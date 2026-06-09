# TryLoadingIconInformationFromShortcut(ushort const *,Dfdll::CString &,uint &)

- ea: `0x180004bcc`
- end: `0x180004ca5`
- name: `?TryLoadingIconInformationFromShortcut@@YAJPEBGAEAVCString@Dfdll@@AEAI@Z`
- size: `217`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const WCHAR **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180002fbc`

## callees

- `0x180004bcc`
- `0x180008a14`
- `0x180008d34`
- `0x18000cac8`
- `0x180010d18`
- `0x180012bd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004c41`
- `KERNEL32!GetLastError` at `0x180004c41`
- `KERNEL32!GetFileAttributesW` at `0x180004c36`
- `KERNEL32!GetFileAttributesW` at `0x180004c36`

## pseudocode

```c
__int64 __fastcall TryLoadingIconInformationFromShortcut(
        const unsigned __int16 *a1,
        const WCHAR **a2,
        unsigned int *a3)
{
  signed int IconInformation; // ebx
  const WCHAR *v7; // rcx
  signed int LastError; // eax
  char v9; // cl
  _BYTE v11[240]; // [rsp+20h] [rbp-118h] BYREF

  Dfdll::CSubscription::CSubscription((Dfdll::CSubscription *)v11);
  IconInformation = Dfdll::CSubscription::LoadFromShortcut((Dfdll::CSubscription *)v11, a1);
  if ( IconInformation >= 0 )
  {
    IconInformation = Dfdll::CSubscription::GetIconInformation(
                        (Dfdll::CSubscription *)v11,
                        (struct Dfdll::CString *)a2,
                        a3);
    if ( IconInformation >= 0 )
    {
      v7 = a2[2];
      if ( v7 )
      {
        if ( GetFileAttributesW(v7) != -1 )
          goto LABEL_11;
        LastError = GetLastError();
        IconInformation = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          IconInformation = LastError;
        if ( IconInformation < 0 )
        {
          if ( (unsigned int)(IconInformation + 2147024894) > 1 )
            goto LABEL_15;
          v9 = 0;
        }
        else
        {
LABEL_11:
          v9 = 1;
        }
        if ( v9 )
          IconInformation = 0;
        else
          IconInformation = -2147024894;
      }
      else
      {
        IconInformation = -2147024809;
      }
    }
  }
LABEL_15:
  Dfdll::CSubscription::~CSubscription((Dfdll::CSubscription *)v11);
  return (unsigned int)IconInformation;
}

```

## disassembly

```asm
0x180004bcc  push    rbx
0x180004bce  push    rsi
0x180004bcf  push    rdi
0x180004bd0  sub     rsp, 120h
0x180004bd7  mov     rax, cs:__security_cookie
0x180004bde  xor     rax, rsp
0x180004be1  mov     [rsp+138h+var_28], rax
0x180004be9  mov     rsi, r8
0x180004bec  mov     rdi, rdx
0x180004bef  mov     rbx, rcx
0x180004bf2  lea     rcx, [rsp+138h+var_118]; this
0x180004bf7  call    ??0CSubscription@Dfdll@@QEAA@XZ; Dfdll::CSubscription::CSubscription(void)
0x180004bfc  nop
0x180004bfd  mov     rdx, rbx; unsigned __int16 *
0x180004c00  lea     rcx, [rsp+138h+var_118]; this
0x180004c05  call    ?LoadFromShortcut@CSubscription@Dfdll@@QEAAJPEBG@Z; Dfdll::CSubscription::LoadFromShortcut(ushort const *)
0x180004c0a  mov     ebx, eax
0x180004c0c  test    eax, eax
0x180004c0e  js      short loc_180004C7E
0x180004c10  mov     r8, rsi; unsigned int *
0x180004c13  mov     rdx, rdi; struct Dfdll::CString *
0x180004c16  lea     rcx, [rsp+138h+var_118]; this
0x180004c1b  call    ?GetIconInformation@CSubscription@Dfdll@@QEAAJAEAVCString@2@AEAI@Z; Dfdll::CSubscription::GetIconInformation(Dfdll::CString &,uint &)
0x180004c20  mov     ebx, eax
0x180004c22  test    eax, eax
0x180004c24  js      short loc_180004C7E
0x180004c26  mov     rcx, [rdi+10h]; lpFileName
0x180004c2a  test    rcx, rcx
0x180004c2d  jnz     short loc_180004C36
0x180004c2f  mov     ebx, 80070057h
0x180004c34  jmp     short loc_180004C7E
0x180004c36  call    cs:__imp_GetFileAttributesW
0x180004c3c  cmp     eax, 0FFFFFFFFh
0x180004c3f  jnz     short loc_180004C6C
0x180004c41  call    cs:__imp_GetLastError
0x180004c47  movzx   ebx, ax
0x180004c4a  or      ebx, 80070000h
0x180004c50  test    eax, eax
0x180004c52  cmovle  ebx, eax
0x180004c55  test    ebx, ebx
0x180004c57  jns     short loc_180004C6C
0x180004c59  lea     eax, [rbx+7FF8FFFEh]
0x180004c5f  mov     ecx, 1
0x180004c64  cmp     eax, ecx
0x180004c66  ja      short loc_180004C7E
0x180004c68  xor     cl, cl
0x180004c6a  jmp     short loc_180004C71
0x180004c6c  mov     ecx, 1
0x180004c71  test    cl, cl
0x180004c73  jnz     short loc_180004C7C
0x180004c75  mov     ebx, 80070002h
0x180004c7a  jmp     short loc_180004C7E
0x180004c7c  xor     ebx, ebx
0x180004c7e  lea     rcx, [rsp+138h+var_118]; this
0x180004c83  call    ??1CSubscription@Dfdll@@QEAA@XZ; Dfdll::CSubscription::~CSubscription(void)
0x180004c88  mov     eax, ebx
0x180004c8a  mov     rcx, [rsp+138h+var_28]
0x180004c92  xor     rcx, rsp; StackCookie
0x180004c95  call    __security_check_cookie
0x180004c9a  add     rsp, 120h
0x180004ca1  pop     rdi
0x180004ca2  pop     rsi
0x180004ca3  pop     rbx
0x180004ca4  retn
```
