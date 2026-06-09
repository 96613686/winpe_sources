# DfscCreateNetUseTreeConnection

- ea: `0x1400136f0`
- end: `0x140013900`
- name: `DfscCreateNetUseTreeConnection`
- size: `528`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, __int64, int, char, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001338c`

## callees

- `0x140004030`
- `0x1400041b8`
- `0x1400131d0`
- `0x1400136f0`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x140013886`
- `ntoskrnl!ZwCreateFile` at `0x140013886`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138d5`

## pseudocode

```c
__int64 __fastcall DfscCreateNetUseTreeConnection(
        struct _UNICODE_STRING *a1,
        __int64 a2,
        int a3,
        char a4,
        unsigned int *a5,
        void **a6)
{
  unsigned int *v6; // rsi
  int v9; // r14d
  unsigned int v10; // r9d
  char *v11; // r8
  NTSTATUS v12; // eax
  int v13; // r8d
  PVOID EaBuffer; // rbx
  NTSTATUS v15; // edi
  ULONG EaLength; // edi
  wchar_t *v17; // rax
  const char *v18; // rdx
  ULONG CreateOptions; // edx
  ULONG FileAttributes; // ecx
  int v21; // edx
  int v22; // r8d
  void *FileHandle; // [rsp+60h] [rbp-39h] BYREF
  __int128 v25; // [rsp+68h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-21h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-11h] BYREF
  PVOID P; // [rsp+F0h] [rbp+57h] BYREF
  ULONG v29; // [rsp+100h] [rbp+67h] BYREF

  v6 = a5;
  FileHandle = 0;
  P = 0;
  v29 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v9 = (int)a1;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a1;
  IoStatusBlock = 0;
  v25 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( a5 )
  {
    v10 = a5[1];
    v11 = (char *)a5 + *a5;
  }
  else
  {
    v11 = 0;
    v10 = 0;
  }
  v12 = DfscCreateEas(a3 == 3, a2, v11, v10, (char **)&P, &v29);
  EaBuffer = P;
  v15 = v12;
  if ( !v12 )
  {
    EaLength = v29;
    if ( P )
    {
      WORD1(v25) = *((_WORD *)P + 3);
      LOWORD(v25) = WORD1(v25);
      *((_QWORD *)&v25 + 1) = (char *)P + *((unsigned __int8 *)P + 5) + 9;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      v17 = (wchar_t *)&v25;
      if ( !P )
        v17 = DfscDefaultLogString;
      v18 = (char *)P + 8;
      if ( !P )
        v18 = "<Def>";
      WPP_SF_ZsZ(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)v18, v13, v9, (__int64)v18, (__int64)v17);
    }
    CreateOptions = 1185;
    if ( a3 != 2 )
      CreateOptions = 161;
    FileAttributes = ((a4 & 2) << 14) | 0x4080;
    if ( (a4 & 4) == 0 )
      FileAttributes = ((a4 & 2) << 14) | 0x80;
    if ( v6 )
      FileAttributes |= v6[3];
    v15 = ZwCreateFile(
            &FileHandle,
            0x100000u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            FileAttributes,
            7u,
            3u,
            CreateOptions,
            EaBuffer,
            EaLength);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_ZD(WPP_GLOBAL_Control->AttachedDevice, v21, v22, v9, v15);
    }
    if ( v15 >= 0 )
      *a6 = FileHandle;
  }
  if ( EaBuffer )
    ExFreePoolWithTag(EaBuffer, 0);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400136f0  mov     [rsp-8+arg_8], rbx
0x1400136f5  mov     [rsp-8+arg_18], rsi
0x1400136fa  push    rbp
0x1400136fb  push    rdi
0x1400136fc  push    r12
0x1400136fe  push    r14
0x140013700  push    r15
0x140013702  lea     rbp, [rsp-27h]
0x140013707  sub     rsp, 0C0h
0x14001370e  mov     rsi, [rbp+47h+arg_20]
0x140013712  xor     eax, eax
0x140013714  mov     [rbp+47h+FileHandle], 0
0x14001371c  xorps   xmm0, xmm0
0x14001371f  mov     [rbp+47h+P], 0
0x140013727  xorps   xmm1, xmm1
0x14001372a  mov     [rbp+47h+arg_10], 0
0x140013731  mov     r15d, r9d
0x140013734  mov     qword ptr [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x14001373c  mov     r12d, r8d
0x14001373f  mov     qword ptr [rbp+47h+ObjectAttributes.Attributes], 240h
0x140013747  mov     r14, rcx
0x14001374a  mov     [rbp+47h+ObjectAttributes.RootDirectory], rax
0x14001374e  mov     [rbp+47h+ObjectAttributes.ObjectName], rcx
0x140013752  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x140013756  movups  [rbp+47h+var_78], xmm1
0x14001375a  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001375f  test    rsi, rsi
0x140013762  jz      short loc_140013770
0x140013764  mov     r8d, [rsi]
0x140013767  mov     r9d, [rsi+4]
0x14001376b  add     r8, rsi
0x14001376e  jmp     short loc_140013776
0x140013770  xor     r8d, r8d
0x140013773  xor     r9d, r9d
0x140013776  lea     rax, [rbp+47h+arg_10]
0x14001377a  cmp     r12d, 3
0x14001377e  mov     qword ptr [rsp+0E0h+FileAttributes], rax
0x140013783  lea     rax, [rbp+47h+P]
0x140013787  setz    cl
0x14001378a  mov     [rsp+0E0h+AllocationSize], rax
0x14001378f  call    DfscCreateEas
0x140013794  mov     rbx, [rbp+47h+P]
0x140013798  mov     edi, eax
0x14001379a  test    eax, eax
0x14001379c  jnz     loc_1400138CB
0x1400137a2  mov     edi, [rbp+47h+arg_10]
0x1400137a5  test    rbx, rbx
0x1400137a8  jz      short loc_1400137C5
0x1400137aa  movzx   eax, word ptr [rbx+6]
0x1400137ae  mov     word ptr [rbp+47h+var_78+2], ax
0x1400137b2  mov     word ptr [rbp+47h+var_78], ax
0x1400137b6  movzx   ecx, byte ptr [rbx+5]
0x1400137ba  add     rcx, 9
0x1400137be  add     rcx, rbx
0x1400137c1  mov     qword ptr [rbp+47h+var_78+8], rcx
0x1400137c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400137cc  lea     rax, WPP_GLOBAL_Control
0x1400137d3  cmp     rcx, rax
0x1400137d6  jz      short loc_140013816
0x1400137d8  test    dword ptr [rcx+2Ch], 400000h
0x1400137df  jz      short loc_140013816
0x1400137e1  lea     rdx, DfscDefaultLogString; "\n\n"
0x1400137e8  test    rbx, rbx
0x1400137eb  lea     rax, [rbp+47h+var_78]
0x1400137ef  cmovz   rax, rdx
0x1400137f3  lea     rdx, [rbx+8]
0x1400137f7  jnz     short loc_140013800
0x1400137f9  lea     rdx, aDef_0; "<Def>"
0x140013800  mov     rcx, [rcx+18h]
0x140013804  mov     r9, r14
0x140013807  mov     qword ptr [rsp+0E0h+FileAttributes], rax
0x14001380c  mov     [rsp+0E0h+AllocationSize], rdx
0x140013811  call    WPP_SF_ZsZ
0x140013816  cmp     r12d, 2
0x14001381a  mov     eax, 0A1h
0x14001381f  mov     edx, 4A1h
0x140013824  cmovnz  edx, eax
0x140013827  mov     eax, r15d
0x14001382a  and     eax, 2
0x14001382d  shl     eax, 0Eh
0x140013830  bts     eax, 7
0x140013834  mov     ecx, eax
0x140013836  bts     ecx, 0Eh
0x14001383a  test    r15b, 4
0x14001383e  cmovz   ecx, eax
0x140013841  test    rsi, rsi
0x140013844  jz      short loc_140013849
0x140013846  or      ecx, [rsi+0Ch]
0x140013849  mov     [rsp+0E0h+EaLength], edi; EaLength
0x14001384d  lea     r9, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x140013851  mov     [rsp+0E0h+EaBuffer], rbx; EaBuffer
0x140013856  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x14001385a  mov     [rsp+0E0h+CreateOptions], edx; CreateOptions
0x14001385e  mov     esi, 100000h
0x140013863  mov     [rsp+0E0h+CreateDisposition], 3; CreateDisposition
0x14001386b  mov     edx, esi; DesiredAccess
0x14001386d  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x140013875  mov     [rsp+0E0h+FileAttributes], ecx; FileAttributes
0x140013879  lea     rcx, [rbp+47h+FileHandle]; FileHandle
0x14001387d  mov     [rsp+0E0h+AllocationSize], 0; AllocationSize
0x140013886  call    cs:__imp_ZwCreateFile
0x14001388d  nop     dword ptr [rax+rax+00h]
0x140013892  mov     edi, eax
0x140013894  mov     rcx, cs:WPP_GLOBAL_Control
0x14001389b  lea     rax, WPP_GLOBAL_Control
0x1400138a2  cmp     rcx, rax
0x1400138a5  jz      short loc_1400138BC
0x1400138a7  test    [rcx+2Ch], esi
0x1400138aa  jz      short loc_1400138BC
0x1400138ac  mov     rcx, [rcx+18h]
0x1400138b0  mov     r9, r14
0x1400138b3  mov     dword ptr [rsp+0E0h+AllocationSize], edi
0x1400138b7  call    WPP_SF_ZD
0x1400138bc  test    edi, edi
0x1400138be  js      short loc_1400138CB
0x1400138c0  mov     rdx, [rbp+47h+arg_28]
0x1400138c4  mov     rax, [rbp+47h+FileHandle]
0x1400138c8  mov     [rdx], rax
0x1400138cb  test    rbx, rbx
0x1400138ce  jz      short loc_1400138E1
0x1400138d0  xor     edx, edx; Tag
0x1400138d2  mov     rcx, rbx; P
0x1400138d5  call    cs:__imp_ExFreePoolWithTag
0x1400138dc  nop     dword ptr [rax+rax+00h]
0x1400138e1  lea     r11, [rsp+0E0h+var_20]
0x1400138e9  mov     eax, edi
0x1400138eb  mov     rbx, [r11+38h]
0x1400138ef  mov     rsi, [r11+48h]
0x1400138f3  mov     rsp, r11
0x1400138f6  pop     r15
0x1400138f8  pop     r14
0x1400138fa  pop     r12
0x1400138fc  pop     rdi
0x1400138fd  pop     rbp
0x1400138fe  retn
```
