# HsmOsStartWppTracing

- ea: `0x1400131fc`
- end: `0x140013673`
- name: `HsmOsStartWppTracing`
- size: `1143`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140042e0c`

## callees

- `0x14000c358`
- `0x1400131fc`
- `0x140014b68`
- `0x14001e140`
- `0x14001e580`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x140013367`
- `ntoskrnl!ZwCreateFile` at `0x140013436`
- `ntoskrnl!ZwCreateFile` at `0x140013367`
- `ntoskrnl!ZwCreateFile` at `0x140013436`
- `ntoskrnl!EtwEnableTrace` at `0x1400135b4`
- `ntoskrnl!EtwEnableTrace` at `0x1400135b4`
- `ntoskrnl!ZwTraceControl` at `0x14001355a`
- `ntoskrnl!ZwTraceControl` at `0x14001355a`
- `ntoskrnl!ZwQueryInformationFile` at `0x140013392`
- `ntoskrnl!ZwQueryInformationFile` at `0x140013392`
- `ntoskrnl!ZwClose` at `0x1400133c0`
- `ntoskrnl!ZwClose` at `0x140013451`
- `ntoskrnl!ZwClose` at `0x140013473`
- `ntoskrnl!ZwClose` at `0x1400133c0`
- `ntoskrnl!ZwClose` at `0x140013451`
- `ntoskrnl!ZwClose` at `0x140013473`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013629`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013641`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013629`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013641`

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
0x1400131fc  push    rbp
0x1400131fe  push    rbx
0x1400131ff  push    rsi
0x140013200  push    rdi
0x140013201  push    r12
0x140013203  push    r13
0x140013205  push    r14
0x140013207  push    r15
0x140013209  lea     rbp, [rsp-0D8h]
0x140013211  sub     rsp, 1D8h
0x140013218  mov     rax, cs:__security_cookie
0x14001321f  xor     rax, rsp
0x140013222  mov     [rbp+110h+var_50], rax
0x140013229  mov     edi, cs:dword_140028E50
0x14001322f  lea     rdx, [rsp+210h+var_1A8]; PUNICODE_STRING
0x140013234  xor     eax, eax
0x140013236  shr     edi, 9
0x140013239  mov     [rbp+110h+var_178], rax
0x14001323d  xorps   xmm0, xmm0
0x140013240  mov     [rbp+110h+var_170], rcx
0x140013244  xorps   xmm1, xmm1
0x140013247  mov     esi, 1
0x14001324c  mov     [rbp+110h+var_188], 0
0x140013253  and     dil, sil
0x140013256  lea     rcx, [rsp+210h+P]; Destination
0x14001325b  mov     al, dil
0x14001325e  neg     al
0x140013260  mov     al, dil
0x140013263  sbb     r15d, r15d
0x140013266  and     r15d, 1FCh
0x14001326d  add     r15d, 4
0x140013271  neg     al
0x140013273  movups  xmmword ptr [rsp+210h+P], xmm0
0x140013278  sbb     r12d, r12d
0x14001327b  and     r12d, 3Ch
0x14001327f  add     r12d, 4
0x140013283  movups  xmmword ptr [rsp+210h+var_1A8], xmm1
0x140013288  call    HsmiOsConstructLogFilesFolder
0x14001328d  xor     r8d, r8d
0x140013290  mov     ebx, eax
0x140013292  test    eax, eax
0x140013294  js      loc_140013619
0x14001329a  movzx   r14d, dil
0x14001329e  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400132a8  xor     r14d, esi
0x1400132ab  mov     [rbp+110h+var_180], rax
0x1400132af  mov     esi, r8d
0x1400132b2  mov     r13b, r8b
0x1400132b5  mov     ebx, r8d
0x1400132b8  lea     ecx, ds:2[r14*2]
0x1400132c0  movzx   eax, bx
0x1400132c3  mov     r9d, 30h ; '0'
0x1400132c9  cmp     eax, ecx
0x1400132cb  jnb     loc_14001348A
0x1400132d1  movzx   ecx, word ptr [rsp+210h+var_1A8]
0x1400132d6  lea     edx, [r9+rbx]
0x1400132da  mov     [rsp+210h+EaLength], r8d; EaLength
0x1400132df  xor     eax, eax
0x1400132e1  mov     [rsp+210h+EaBuffer], r8; EaBuffer
0x1400132e6  xorps   xmm0, xmm0
0x1400132e9  mov     [rsp+210h+CreateOptions], r8d; CreateOptions
0x1400132ee  xorps   xmm1, xmm1
0x1400132f1  mov     [rbp+110h+var_108], rax
0x1400132f5  mov     rax, [rsp+210h+var_1A8+8]
0x1400132fa  shr     rcx, 1
0x1400132fd  mov     [rsp+210h+CreateDisposition], 1; CreateDisposition
0x140013305  mov     [rsp+210h+FileHandle], r8
0x14001330a  mov     dword ptr [rbp+110h+ObjectAttributes+4], r8d
0x14001330e  mov     dword ptr [rbp+110h+ObjectAttributes+1Ch], r8d
0x140013312  movups  xmmword ptr [rbp+110h+IoStatusBlock], xmm0
0x140013316  mov     [rsp+210h+ShareAccess], 7; ShareAccess
0x14001331e  movups  [rbp+110h+FileInformation], xmm1
0x140013322  mov     [rsp+210h+FileAttributes], 80h; FileAttributes
0x14001332a  movups  [rbp+110h+var_118], xmm1
0x14001332e  mov     [rax+rcx*2-0Ah], dx
0x140013333  lea     rax, [rsp+210h+var_1A8]
0x140013338  mov     [rbp+110h+ObjectAttributes.Length], r9d
0x14001333c  lea     rcx, [rsp+210h+FileHandle]; FileHandle
0x140013341  mov     [rbp+110h+ObjectAttributes.RootDirectory], r8
0x140013345  lea     r9, [rbp+110h+IoStatusBlock]; IoStatusBlock
0x140013349  mov     [rsp+210h+AllocationSize], r8; AllocationSize
0x14001334e  mov     edx, 100080h; DesiredAccess
0x140013353  lea     r8, [rbp+110h+ObjectAttributes]; ObjectAttributes
0x140013357  mov     [rbp+110h+ObjectAttributes.ObjectName], rax
0x14001335b  mov     [rbp+110h+ObjectAttributes.Attributes], 240h
0x140013362  movdqu  xmmword ptr [rbp+110h+ObjectAttributes.SecurityDescriptor], xmm0
0x140013367  call    cs:__imp_ZwCreateFile
0x14001336e  nop     dword ptr [rax+rax+00h]
0x140013373  xor     ecx, ecx
0x140013375  test    eax, eax
0x140013377  js      short loc_1400133D7
0x140013379  lea     r9d, [rcx+28h]; Length
0x14001337d  mov     dword ptr [rsp+210h+AllocationSize], 4; FileInformationClass
0x140013385  mov     rcx, [rsp+210h+FileHandle]; FileHandle
0x14001338a  lea     r8, [rbp+110h+FileInformation]; FileInformation
0x14001338e  lea     rdx, [rbp+110h+IoStatusBlock]; IoStatusBlock
0x140013392  call    cs:__imp_ZwQueryInformationFile
0x140013399  nop     dword ptr [rax+rax+00h]
0x14001339e  test    eax, eax
0x1400133a0  js      loc_14001346B
0x1400133a6  mov     rax, [rbp+110h+var_180]
0x1400133aa  cmp     qword ptr [rbp+110h+var_118], rax
0x1400133ae  jge     short loc_1400133BB
0x1400133b0  mov     rax, qword ptr [rbp+110h+var_118]
0x1400133b4  movzx   esi, bx
0x1400133b7  mov     [rbp+110h+var_180], rax
0x1400133bb  mov     rcx, [rsp+210h+FileHandle]; Handle
0x1400133c0  call    cs:__imp_ZwClose
0x1400133c7  nop     dword ptr [rax+rax+00h]
0x1400133cc  inc     bx
0x1400133cf  xor     r8d, r8d
0x1400133d2  jmp     loc_1400132B8
0x1400133d7  test    bx, bx
0x1400133da  jnz     loc_140013481
0x1400133e0  test    r13b, r13b
0x1400133e3  jnz     loc_140013481
0x1400133e9  mov     [rsp+210h+EaLength], ecx; EaLength
0x1400133ed  lea     r9, [rbp+110h+IoStatusBlock]; IoStatusBlock
0x1400133f1  mov     [rsp+210h+EaBuffer], rcx; EaBuffer
0x1400133f6  lea     r8, [rbp+110h+ObjectAttributes]; ObjectAttributes
0x1400133fa  mov     eax, 0FFEAh
0x1400133ff  mov     r13d, 1
0x140013405  add     word ptr [rsp+210h+var_1A8], ax
0x14001340a  mov     edx, 100100h; DesiredAccess
0x14001340f  mov     [rsp+210h+CreateOptions], r13d; CreateOptions
0x140013414  mov     [rsp+210h+CreateDisposition], 3; CreateDisposition
0x14001341c  mov     [rsp+210h+ShareAccess], 7; ShareAccess
0x140013424  mov     [rsp+210h+FileAttributes], 80h; FileAttributes
0x14001342c  mov     [rsp+210h+AllocationSize], rcx; AllocationSize
0x140013431  lea     rcx, [rsp+210h+FileHandle]; FileHandle
0x140013436  call    cs:__imp_ZwCreateFile
0x14001343d  nop     dword ptr [rax+rax+00h]
0x140013442  mov     ebx, eax
0x140013444  test    eax, eax
0x140013446  js      loc_140013619
0x14001344c  mov     rcx, [rsp+210h+FileHandle]; Handle
0x140013451  call    cs:__imp_ZwClose
0x140013458  nop     dword ptr [rax+rax+00h]
0x14001345d  add     word ptr [rsp+210h+var_1A8], 16h
0x140013463  xor     r8d, r8d
0x140013466  jmp     loc_1400132B5
0x14001346b  mov     rcx, [rsp+210h+FileHandle]; Handle
0x140013470  movzx   esi, bx
0x140013473  call    cs:__imp_ZwClose
0x14001347a  nop     dword ptr [rax+rax+00h]
0x14001347f  jmp     short loc_140013484
0x140013481  movzx   esi, bx
0x140013484  mov     r9d, 30h ; '0'
0x14001348a  movzx   ecx, word ptr [rsp+210h+P]
0x14001348f  add     si, r9w
0x140013493  mov     rax, [rbp+110h+P+8]
0x140013497  xor     edx, edx; Val
0x140013499  shr     rcx, 1
0x14001349c  mov     [rax+rcx*2-0Ah], si
0x1400134a1  mov     esi, 0B0h
0x1400134a6  mov     r8d, esi; Size
0x1400134a9  lea     rcx, [rbp+110h+var_100]; void *
0x1400134ad  call    memset
0x1400134b2  mov     rax, [rbp+110h+var_178]
0x1400134b6  lea     r9, [rbp+110h+var_100]
0x1400134ba  mov     rbx, [rbp+110h+var_170]
0x1400134be  lea     rdx, [rbp+110h+var_100]
0x1400134c2  mov     [rbp+110h+var_6C], eax
0x1400134c8  mov     r8d, esi
0x1400134cb  lea     rax, aCldfltlog; "CldFltLog"
0x1400134d2  shl     r14d, 1Ch
0x1400134d6  mov     [rbp+110h+var_68], rax
0x1400134dd  sub     r14d, 7FFFFDFEh
0x1400134e4  movups  xmm0, xmmword ptr [rbx]
0x1400134e7  mov     eax, 2
0x1400134ec  mov     [rbp+110h+var_C0], r14d
0x1400134f0  mov     [rbp+110h+var_D8], eax
0x1400134f3  mov     r14d, 1
0x1400134f9  mov     [rbp+110h+var_CC], eax
0x1400134fc  mov     ecx, r14d
0x1400134ff  movzx   eax, word ptr [rsp+210h+P]
0x140013504  mov     [rbp+110h+var_80], ax
0x14001350b  mov     eax, dword ptr [rsp+210h+P+2]
0x14001350f  mov     [rbp+110h+var_7E], eax
0x140013515  movzx   eax, word ptr [rsp+210h+P+6]
0x14001351a  mov     [rbp+110h+var_7A], ax
0x140013521  mov     rax, [rbp+110h+P+8]
0x140013525  mov     [rbp+110h+var_78], rax
0x14001352c  lea     rax, [rbp+110h+var_188]
0x140013530  mov     qword ptr [rsp+210h+FileAttributes], rax
0x140013535  mov     dword ptr [rsp+210h+AllocationSize], esi
0x140013539  mov     [rbp+110h+var_70], 140012h
0x140013543  movdqu  [rbp+110h+var_E8], xmm0
0x140013548  mov     [rbp+110h+var_100], esi
0x14001354b  mov     [rbp+110h+var_D4], 20000h
0x140013552  mov     [rbp+110h+var_D0], r12d
0x140013556  mov     [rbp+110h+var_C4], r15d
0x14001355a  call    cs:__imp_ZwTraceControl
0x140013561  nop     dword ptr [rax+rax+00h]
0x140013566  xor     r8d, r8d
0x140013569  test    eax, eax
0x14001356b  js      loc_1400135FA
0x140013571  movzx   esi, [rbp+110h+var_F8]
0x140013575  add     dil, r14b
0x140013578  add     dil, dil
0x14001357b  mov     [rsp+210h+FileHandle], r8
0x140013580  test    si, si
0x140013583  jnz     short loc_14001358A
0x140013585  mov     esi, 0FFFFh
0x14001358a  mov     [rsp+210h+CreateDisposition], r8d
0x14001358f  mov     r9d, r14d
0x140013592  mov     qword ptr [rsp+210h+ShareAccess], r8
0x140013597  xor     edx, edx
0x140013599  mov     word ptr [rsp+210h+FileHandle], si
0x14001359e  mov     rcx, rbx
0x1400135a1  mov     r8, [rsp+210h+FileHandle]
0x1400135a6  mov     qword ptr [rsp+210h+FileAttributes], 11Fh
0x1400135af  mov     byte ptr [rsp+210h+AllocationSize], dil
0x1400135b4  call    cs:__imp_EtwEnableTrace
0x1400135bb  nop     dword ptr [rax+rax+00h]
0x1400135c0  xor     r8d, r8d
0x1400135c3  mov     ebx, eax
0x1400135c5  test    eax, eax
0x1400135c7  jns     short loc_1400135DB
0x1400135c9  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, r14b
0x1400135d0  jz      short loc_140013616
0x1400135d2  lea     r9, aEnablingCldflt; "Enabling Cldflt Tracing failed."
0x1400135d9  jmp     short loc_14001360A
0x1400135db  mov     eax, dword ptr [rsp+210h+FileHandle+2]
0x1400135df  mov     dword ptr cs:qword_1400290E8+2, eax
0x1400135e5  movzx   eax, word ptr [rsp+210h+FileHandle+6]
0x1400135ea  mov     word ptr cs:qword_1400290E8+6, ax
0x1400135f1  mov     word ptr cs:qword_1400290E8, si
0x1400135f8  jmp     short loc_140013619
0x1400135fa  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, r14b
0x140013601  jz      short loc_140013616
0x140013603  lea     r9, aStartingCldflt; "Starting Cldflt Tracing failed."
0x14001360a  mov     dword ptr [rsp+210h+AllocationSize], eax
0x14001360e  call    McTemplateK0zd_EtwWriteTransfer
0x140013613  xor     r8d, r8d
0x140013616  mov     ebx, r8d
0x140013619  mov     rcx, [rbp+110h+P+8]; P
0x14001361d  mov     edi, 73557348h
0x140013622  test    rcx, rcx
0x140013625  jz      short loc_140013635
0x140013627  mov     edx, edi; Tag
0x140013629  call    cs:__imp_ExFreePoolWithTag
0x140013630  nop     dword ptr [rax+rax+00h]
0x140013635  mov     rcx, [rsp+210h+var_1A8+8]; P
0x14001363a  test    rcx, rcx
0x14001363d  jz      short loc_14001364D
0x14001363f  mov     edx, edi; Tag
0x140013641  call    cs:__imp_ExFreePoolWithTag
0x140013648  nop     dword ptr [rax+rax+00h]
0x14001364d  mov     eax, ebx
0x14001364f  mov     rcx, [rbp+110h+var_50]
0x140013656  xor     rcx, rsp; StackCookie
0x140013659  call    __security_check_cookie
0x14001365e  add     rsp, 1D8h
0x140013665  pop     r15
0x140013667  pop     r14
0x140013669  pop     r13
0x14001366b  pop     r12
0x14001366d  pop     rdi
0x14001366e  pop     rsi
0x14001366f  pop     rbx
0x140013670  pop     rbp
0x140013671  retn
```
