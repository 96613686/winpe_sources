# HsmOsStartWppTracing

- ea: `0x14001327c`
- end: `0x1400136f3`
- name: `HsmOsStartWppTracing`
- size: `1143`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140042efc`

## callees

- `0x14000c358`
- `0x14001327c`
- `0x140014be8`
- `0x14001e1c0`
- `0x14001e600`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x1400133e7`
- `ntoskrnl!ZwCreateFile` at `0x1400134b6`
- `ntoskrnl!ZwCreateFile` at `0x1400133e7`
- `ntoskrnl!ZwCreateFile` at `0x1400134b6`
- `ntoskrnl!EtwEnableTrace` at `0x140013634`
- `ntoskrnl!EtwEnableTrace` at `0x140013634`
- `ntoskrnl!ZwTraceControl` at `0x1400135da`
- `ntoskrnl!ZwTraceControl` at `0x1400135da`
- `ntoskrnl!ZwQueryInformationFile` at `0x140013412`
- `ntoskrnl!ZwQueryInformationFile` at `0x140013412`
- `ntoskrnl!ZwClose` at `0x140013440`
- `ntoskrnl!ZwClose` at `0x1400134d1`
- `ntoskrnl!ZwClose` at `0x1400134f3`
- `ntoskrnl!ZwClose` at `0x140013440`
- `ntoskrnl!ZwClose` at `0x1400134d1`
- `ntoskrnl!ZwClose` at `0x1400134f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136c1`

## pseudocode

```c
__int64 __fastcall HsmOsStartWppTracing(_OWORD *a1)
{
  bool v1; // di
  NTSTATUS v2; // ebx
  int v3; // r14d
  unsigned __int16 v4; // si
  char v5; // r13
  unsigned __int16 i; // bx
  _OWORD *v7; // rbx
  __int128 v8; // xmm0
  int v9; // eax
  int v10; // edx
  int v11; // ecx
  __int16 v12; // si
  char v13; // di
  const wchar_t *v14; // r9
  int AllocationSize; // [rsp+20h] [rbp-E0h]
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  PVOID v18[2]; // [rsp+68h] [rbp-98h] BYREF
  PVOID P[2]; // [rsp+78h] [rbp-88h] BYREF
  int v20; // [rsp+88h] [rbp-78h] BYREF
  __int64 v21; // [rsp+90h] [rbp-70h]
  __int64 v22; // [rsp+98h] [rbp-68h]
  _OWORD *v23; // [rsp+A0h] [rbp-60h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v27; // [rsp+F8h] [rbp-8h]
  __int64 v28; // [rsp+108h] [rbp+8h]
  _QWORD v29[22]; // [rsp+110h] [rbp+10h] BYREF

  v22 = 0;
  v23 = a1;
  v20 = 0;
  v1 = (dword_140028E50 & 0x200) != 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)v18 = 0;
  v2 = HsmiOsConstructLogFilesFolder((PUNICODE_STRING)P, (PUNICODE_STRING)v18);
  if ( v2 >= 0 )
  {
    v3 = !v1;
    v21 = 0x7FFFFFFFFFFFFFFFLL;
    v4 = 0;
    v5 = 0;
LABEL_3:
    for ( i = 0; i < (unsigned int)(2 * v3 + 2); ++i )
    {
      v28 = 0;
      FileHandle = 0;
      *(&ObjectAttributes.Length + 1) = 0;
      *(&ObjectAttributes.Attributes + 1) = 0;
      IoStatusBlock = 0;
      FileInformation = 0;
      v27 = 0;
      *((_WORD *)v18[1] + ((unsigned __int64)LOWORD(v18[0]) >> 1) - 5) = i + 48;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v18;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwCreateFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0, 0, 0) < 0 )
      {
        if ( i || v5 )
        {
          v4 = i;
          break;
        }
        v5 = 1;
        LOWORD(v18[0]) -= 22;
        v2 = ZwCreateFile(&FileHandle, 0x100100u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 3u, 1u, 0, 0);
        if ( v2 < 0 )
          goto LABEL_27;
        ZwClose(FileHandle);
        LOWORD(v18[0]) += 22;
        goto LABEL_3;
      }
      if ( ZwQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation) < 0 )
      {
        v4 = i;
        ZwClose(FileHandle);
        break;
      }
      if ( (__int64)v27 < v21 )
      {
        v4 = i;
        v21 = v27;
      }
      ZwClose(FileHandle);
    }
    *((_WORD *)P[1] + ((unsigned __int64)LOWORD(P[0]) >> 1) - 5) = v4 + 48;
    memset(v29, 0, sizeof(v29));
    v7 = v23;
    HIDWORD(v29[18]) = v22;
    v29[19] = L"CldFltLog";
    v8 = *v23;
    LODWORD(v29[8]) = (v3 << 28) - 2147483134;
    v29[5] = 0x2000000000002LL;
    HIDWORD(v29[6]) = 2;
    v29[16] = P[0];
    v29[17] = P[1];
    LODWORD(v29[18]) = 1310738;
    *(_OWORD *)&v29[3] = v8;
    LODWORD(v29[0]) = 176;
    LODWORD(v29[6]) = v1 ? 64 : 4;
    HIDWORD(v29[7]) = v1 ? 512 : 4;
    v9 = ZwTraceControl(1, v29, 176, v29, 176, &v20);
    if ( v9 < 0 )
    {
      if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) == 0 )
      {
LABEL_26:
        v2 = 0;
        goto LABEL_27;
      }
      v14 = L"Starting Cldflt Tracing failed.";
    }
    else
    {
      v12 = v29[1];
      v13 = 2 * (v1 + 1);
      FileHandle = 0;
      if ( !LOWORD(v29[1]) )
        v12 = -1;
      LOWORD(FileHandle) = v12;
      LOBYTE(AllocationSize) = v13;
      v9 = EtwEnableTrace(v7, 0, FileHandle, 1, AllocationSize, 287, 0, 0);
      v2 = v9;
      if ( v9 >= 0 )
      {
        *(_DWORD *)((char *)&qword_1400290E8 + 2) = *(_DWORD *)((char *)&FileHandle + 2);
        HIWORD(qword_1400290E8) = HIWORD(FileHandle);
        LOWORD(qword_1400290E8) = v12;
        goto LABEL_27;
      }
      if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) == 0 )
        goto LABEL_26;
      v14 = L"Enabling Cldflt Tracing failed.";
    }
    McTemplateK0zd_EtwWriteTransfer(v11, v10, 0, (_DWORD)v14, v9);
    goto LABEL_26;
  }
LABEL_27:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x73557348u);
  if ( v18[1] )
    ExFreePoolWithTag(v18[1], 0x73557348u);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14001327c  push    rbp
0x14001327e  push    rbx
0x14001327f  push    rsi
0x140013280  push    rdi
0x140013281  push    r12
0x140013283  push    r13
0x140013285  push    r14
0x140013287  push    r15
0x140013289  lea     rbp, [rsp-0D8h]
0x140013291  sub     rsp, 1D8h
0x140013298  mov     rax, cs:__security_cookie
0x14001329f  xor     rax, rsp
0x1400132a2  mov     [rbp+110h+var_50], rax
0x1400132a9  mov     edi, cs:dword_140028E50
0x1400132af  lea     rdx, [rsp+210h+var_1A8]; PUNICODE_STRING
0x1400132b4  xor     eax, eax
0x1400132b6  shr     edi, 9
0x1400132b9  mov     [rbp+110h+var_178], rax
0x1400132bd  xorps   xmm0, xmm0
0x1400132c0  mov     [rbp+110h+var_170], rcx
0x1400132c4  xorps   xmm1, xmm1
0x1400132c7  mov     esi, 1
0x1400132cc  mov     [rbp+110h+var_188], 0
0x1400132d3  and     dil, sil
0x1400132d6  lea     rcx, [rsp+210h+P]; Destination
0x1400132db  mov     al, dil
0x1400132de  neg     al
0x1400132e0  mov     al, dil
0x1400132e3  sbb     r15d, r15d
0x1400132e6  and     r15d, 1FCh
0x1400132ed  add     r15d, 4
0x1400132f1  neg     al
0x1400132f3  movups  xmmword ptr [rsp+210h+P], xmm0
0x1400132f8  sbb     r12d, r12d
0x1400132fb  and     r12d, 3Ch
0x1400132ff  add     r12d, 4
0x140013303  movups  xmmword ptr [rsp+210h+var_1A8], xmm1
0x140013308  call    HsmiOsConstructLogFilesFolder
0x14001330d  xor     r8d, r8d
0x140013310  mov     ebx, eax
0x140013312  test    eax, eax
0x140013314  js      loc_140013699
0x14001331a  movzx   r14d, dil
0x14001331e  mov     rax, 7FFFFFFFFFFFFFFFh
0x140013328  xor     r14d, esi
0x14001332b  mov     [rbp+110h+var_180], rax
0x14001332f  mov     esi, r8d
0x140013332  mov     r13b, r8b
0x140013335  mov     ebx, r8d
0x140013338  lea     ecx, ds:2[r14*2]
0x140013340  movzx   eax, bx
0x140013343  mov     r9d, 30h ; '0'
0x140013349  cmp     eax, ecx
0x14001334b  jnb     loc_14001350A
0x140013351  movzx   ecx, word ptr [rsp+210h+var_1A8]
0x140013356  lea     edx, [r9+rbx]
0x14001335a  mov     [rsp+210h+EaLength], r8d; EaLength
0x14001335f  xor     eax, eax
0x140013361  mov     [rsp+210h+EaBuffer], r8; EaBuffer
0x140013366  xorps   xmm0, xmm0
0x140013369  mov     [rsp+210h+CreateOptions], r8d; CreateOptions
0x14001336e  xorps   xmm1, xmm1
0x140013371  mov     [rbp+110h+var_108], rax
0x140013375  mov     rax, [rsp+210h+var_1A8+8]
0x14001337a  shr     rcx, 1
0x14001337d  mov     [rsp+210h+CreateDisposition], 1; CreateDisposition
0x140013385  mov     [rsp+210h+FileHandle], r8
0x14001338a  mov     dword ptr [rbp+110h+ObjectAttributes+4], r8d
0x14001338e  mov     dword ptr [rbp+110h+ObjectAttributes+1Ch], r8d
0x140013392  movups  xmmword ptr [rbp+110h+IoStatusBlock], xmm0
0x140013396  mov     [rsp+210h+ShareAccess], 7; ShareAccess
0x14001339e  movups  [rbp+110h+FileInformation], xmm1
0x1400133a2  mov     [rsp+210h+FileAttributes], 80h; FileAttributes
0x1400133aa  movups  [rbp+110h+var_118], xmm1
0x1400133ae  mov     [rax+rcx*2-0Ah], dx
0x1400133b3  lea     rax, [rsp+210h+var_1A8]
0x1400133b8  mov     [rbp+110h+ObjectAttributes.Length], r9d
0x1400133bc  lea     rcx, [rsp+210h+FileHandle]; FileHandle
0x1400133c1  mov     [rbp+110h+ObjectAttributes.RootDirectory], r8
0x1400133c5  lea     r9, [rbp+110h+IoStatusBlock]; IoStatusBlock
0x1400133c9  mov     [rsp+210h+AllocationSize], r8; AllocationSize
0x1400133ce  mov     edx, 100080h; DesiredAccess
0x1400133d3  lea     r8, [rbp+110h+ObjectAttributes]; ObjectAttributes
0x1400133d7  mov     [rbp+110h+ObjectAttributes.ObjectName], rax
0x1400133db  mov     [rbp+110h+ObjectAttributes.Attributes], 240h
0x1400133e2  movdqu  xmmword ptr [rbp+110h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400133e7  call    cs:__imp_ZwCreateFile
0x1400133ee  nop     dword ptr [rax+rax+00h]
0x1400133f3  xor     ecx, ecx
0x1400133f5  test    eax, eax
0x1400133f7  js      short loc_140013457
0x1400133f9  lea     r9d, [rcx+28h]; Length
0x1400133fd  mov     dword ptr [rsp+210h+AllocationSize], 4; FileInformationClass
0x140013405  mov     rcx, [rsp+210h+FileHandle]; FileHandle
0x14001340a  lea     r8, [rbp+110h+FileInformation]; FileInformation
0x14001340e  lea     rdx, [rbp+110h+IoStatusBlock]; IoStatusBlock
0x140013412  call    cs:__imp_ZwQueryInformationFile
0x140013419  nop     dword ptr [rax+rax+00h]
0x14001341e  test    eax, eax
0x140013420  js      loc_1400134EB
0x140013426  mov     rax, [rbp+110h+var_180]
0x14001342a  cmp     qword ptr [rbp+110h+var_118], rax
0x14001342e  jge     short loc_14001343B
0x140013430  mov     rax, qword ptr [rbp+110h+var_118]
0x140013434  movzx   esi, bx
0x140013437  mov     [rbp+110h+var_180], rax
0x14001343b  mov     rcx, [rsp+210h+FileHandle]; Handle
0x140013440  call    cs:__imp_ZwClose
0x140013447  nop     dword ptr [rax+rax+00h]
0x14001344c  inc     bx
0x14001344f  xor     r8d, r8d
0x140013452  jmp     loc_140013338
0x140013457  test    bx, bx
0x14001345a  jnz     loc_140013501
0x140013460  test    r13b, r13b
0x140013463  jnz     loc_140013501
0x140013469  mov     [rsp+210h+EaLength], ecx; EaLength
0x14001346d  lea     r9, [rbp+110h+IoStatusBlock]; IoStatusBlock
0x140013471  mov     [rsp+210h+EaBuffer], rcx; EaBuffer
0x140013476  lea     r8, [rbp+110h+ObjectAttributes]; ObjectAttributes
0x14001347a  mov     eax, 0FFEAh
0x14001347f  mov     r13d, 1
0x140013485  add     word ptr [rsp+210h+var_1A8], ax
0x14001348a  mov     edx, 100100h; DesiredAccess
0x14001348f  mov     [rsp+210h+CreateOptions], r13d; CreateOptions
0x140013494  mov     [rsp+210h+CreateDisposition], 3; CreateDisposition
0x14001349c  mov     [rsp+210h+ShareAccess], 7; ShareAccess
0x1400134a4  mov     [rsp+210h+FileAttributes], 80h; FileAttributes
0x1400134ac  mov     [rsp+210h+AllocationSize], rcx; AllocationSize
0x1400134b1  lea     rcx, [rsp+210h+FileHandle]; FileHandle
0x1400134b6  call    cs:__imp_ZwCreateFile
0x1400134bd  nop     dword ptr [rax+rax+00h]
0x1400134c2  mov     ebx, eax
0x1400134c4  test    eax, eax
0x1400134c6  js      loc_140013699
0x1400134cc  mov     rcx, [rsp+210h+FileHandle]; Handle
0x1400134d1  call    cs:__imp_ZwClose
0x1400134d8  nop     dword ptr [rax+rax+00h]
0x1400134dd  add     word ptr [rsp+210h+var_1A8], 16h
0x1400134e3  xor     r8d, r8d
0x1400134e6  jmp     loc_140013335
0x1400134eb  mov     rcx, [rsp+210h+FileHandle]; Handle
0x1400134f0  movzx   esi, bx
0x1400134f3  call    cs:__imp_ZwClose
0x1400134fa  nop     dword ptr [rax+rax+00h]
0x1400134ff  jmp     short loc_140013504
0x140013501  movzx   esi, bx
0x140013504  mov     r9d, 30h ; '0'
0x14001350a  movzx   ecx, word ptr [rsp+210h+P]
0x14001350f  add     si, r9w
0x140013513  mov     rax, [rbp+110h+P+8]
0x140013517  xor     edx, edx; Val
0x140013519  shr     rcx, 1
0x14001351c  mov     [rax+rcx*2-0Ah], si
0x140013521  mov     esi, 0B0h
0x140013526  mov     r8d, esi; Size
0x140013529  lea     rcx, [rbp+110h+var_100]; void *
0x14001352d  call    memset
0x140013532  mov     rax, [rbp+110h+var_178]
0x140013536  lea     r9, [rbp+110h+var_100]
0x14001353a  mov     rbx, [rbp+110h+var_170]
0x14001353e  lea     rdx, [rbp+110h+var_100]
0x140013542  mov     [rbp+110h+var_6C], eax
0x140013548  mov     r8d, esi
0x14001354b  lea     rax, aCldfltlog; "CldFltLog"
0x140013552  shl     r14d, 1Ch
0x140013556  mov     [rbp+110h+var_68], rax
0x14001355d  sub     r14d, 7FFFFDFEh
0x140013564  movups  xmm0, xmmword ptr [rbx]
0x140013567  mov     eax, 2
0x14001356c  mov     [rbp+110h+var_C0], r14d
0x140013570  mov     [rbp+110h+var_D8], eax
0x140013573  mov     r14d, 1
0x140013579  mov     [rbp+110h+var_CC], eax
0x14001357c  mov     ecx, r14d
0x14001357f  movzx   eax, word ptr [rsp+210h+P]
0x140013584  mov     [rbp+110h+var_80], ax
0x14001358b  mov     eax, dword ptr [rsp+210h+P+2]
0x14001358f  mov     [rbp+110h+var_7E], eax
0x140013595  movzx   eax, word ptr [rsp+210h+P+6]
0x14001359a  mov     [rbp+110h+var_7A], ax
0x1400135a1  mov     rax, [rbp+110h+P+8]
0x1400135a5  mov     [rbp+110h+var_78], rax
0x1400135ac  lea     rax, [rbp+110h+var_188]
0x1400135b0  mov     qword ptr [rsp+210h+FileAttributes], rax
0x1400135b5  mov     dword ptr [rsp+210h+AllocationSize], esi
0x1400135b9  mov     [rbp+110h+var_70], 140012h
0x1400135c3  movdqu  [rbp+110h+var_E8], xmm0
0x1400135c8  mov     [rbp+110h+var_100], esi
0x1400135cb  mov     [rbp+110h+var_D4], 20000h
0x1400135d2  mov     [rbp+110h+var_D0], r12d
0x1400135d6  mov     [rbp+110h+var_C4], r15d
0x1400135da  call    cs:__imp_ZwTraceControl
0x1400135e1  nop     dword ptr [rax+rax+00h]
0x1400135e6  xor     r8d, r8d
0x1400135e9  test    eax, eax
0x1400135eb  js      loc_14001367A
0x1400135f1  movzx   esi, [rbp+110h+var_F8]
0x1400135f5  add     dil, r14b
0x1400135f8  add     dil, dil
0x1400135fb  mov     [rsp+210h+FileHandle], r8
0x140013600  test    si, si
0x140013603  jnz     short loc_14001360A
0x140013605  mov     esi, 0FFFFh
0x14001360a  mov     [rsp+210h+CreateDisposition], r8d
0x14001360f  mov     r9d, r14d
0x140013612  mov     qword ptr [rsp+210h+ShareAccess], r8
0x140013617  xor     edx, edx
0x140013619  mov     word ptr [rsp+210h+FileHandle], si
0x14001361e  mov     rcx, rbx
0x140013621  mov     r8, [rsp+210h+FileHandle]
0x140013626  mov     qword ptr [rsp+210h+FileAttributes], 11Fh
0x14001362f  mov     byte ptr [rsp+210h+AllocationSize], dil
0x140013634  call    cs:__imp_EtwEnableTrace
0x14001363b  nop     dword ptr [rax+rax+00h]
0x140013640  xor     r8d, r8d
0x140013643  mov     ebx, eax
0x140013645  test    eax, eax
0x140013647  jns     short loc_14001365B
0x140013649  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, r14b
0x140013650  jz      short loc_140013696
0x140013652  lea     r9, aEnablingCldflt; "Enabling Cldflt Tracing failed."
0x140013659  jmp     short loc_14001368A
0x14001365b  mov     eax, dword ptr [rsp+210h+FileHandle+2]
0x14001365f  mov     dword ptr cs:qword_1400290E8+2, eax
0x140013665  movzx   eax, word ptr [rsp+210h+FileHandle+6]
0x14001366a  mov     word ptr cs:qword_1400290E8+6, ax
0x140013671  mov     word ptr cs:qword_1400290E8, si
0x140013678  jmp     short loc_140013699
0x14001367a  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, r14b
0x140013681  jz      short loc_140013696
0x140013683  lea     r9, aStartingCldflt; "Starting Cldflt Tracing failed."
0x14001368a  mov     dword ptr [rsp+210h+AllocationSize], eax
0x14001368e  call    McTemplateK0zd_EtwWriteTransfer
0x140013693  xor     r8d, r8d
0x140013696  mov     ebx, r8d
0x140013699  mov     rcx, [rbp+110h+P+8]; P
0x14001369d  mov     edi, 73557348h
0x1400136a2  test    rcx, rcx
0x1400136a5  jz      short loc_1400136B5
0x1400136a7  mov     edx, edi; Tag
0x1400136a9  call    cs:__imp_ExFreePoolWithTag
0x1400136b0  nop     dword ptr [rax+rax+00h]
0x1400136b5  mov     rcx, [rsp+210h+var_1A8+8]; P
0x1400136ba  test    rcx, rcx
0x1400136bd  jz      short loc_1400136CD
0x1400136bf  mov     edx, edi; Tag
0x1400136c1  call    cs:__imp_ExFreePoolWithTag
0x1400136c8  nop     dword ptr [rax+rax+00h]
0x1400136cd  mov     eax, ebx
0x1400136cf  mov     rcx, [rbp+110h+var_50]
0x1400136d6  xor     rcx, rsp; StackCookie
0x1400136d9  call    __security_check_cookie
0x1400136de  add     rsp, 1D8h
0x1400136e5  pop     r15
0x1400136e7  pop     r14
0x1400136e9  pop     r13
0x1400136eb  pop     r12
0x1400136ed  pop     rdi
0x1400136ee  pop     rsi
0x1400136ef  pop     rbx
0x1400136f0  pop     rbp
0x1400136f1  retn
```
