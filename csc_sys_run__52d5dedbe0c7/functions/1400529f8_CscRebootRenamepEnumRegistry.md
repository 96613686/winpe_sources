# CscRebootRenamepEnumRegistry

- ea: `0x1400529f8`
- end: `0x140052d3a`
- name: `CscRebootRenamepEnumRegistry`
- size: `834`
- prototype: `__int64 __fastcall(int, int, int, int, PERESOURCE Resource)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140052520`

## callees

- `0x1400190ec`
- `0x14001d504`
- `0x140021704`
- `0x1400218ac`
- `0x14002f010`
- `0x1400529f8`
- `0x140052d40`
- `0x140052e44`
- `0x140052f74`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140052cd7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140052cd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052c14`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052c2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052c9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052cbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052c14`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052c2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052c9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052cbb`
- `ntoskrnl!ZwClose` at `0x140052c85`
- `ntoskrnl!ZwClose` at `0x140052c85`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140052b16`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140052b16`
- `ntoskrnl!ZwDeleteKey` at `0x140052c74`
- `ntoskrnl!ZwDeleteKey` at `0x140052c74`

## pseudocode

```c
__int64 __fastcall CscRebootRenamepEnumRegistry(
        struct _UNICODE_STRING *a1,
        __int64 a2,
        int a3,
        unsigned int *a4,
        PERESOURCE Resource)
{
  int v8; // eax
  int IndexString; // ebx
  char v10; // r14
  int v11; // edi
  __int64 v12; // rcx
  int v13; // eax
  PVOID v14; // rcx
  HANDLE v15; // rcx
  HANDLE KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v18; // [rsp+58h] [rbp-A8h]
  struct _UNICODE_STRING v19; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING v20; // [rsp+70h] [rbp-90h] BYREF
  PVOID P[2]; // [rsp+80h] [rbp-80h] BYREF
  PVOID v22[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v24; // [rsp+B0h] [rbp-50h]
  char *v25; // [rsp+B8h] [rbp-48h]
  char v26; // [rsp+C0h] [rbp-40h] BYREF
  char v27; // [rsp+D0h] [rbp-30h] BYREF
  char v28; // [rsp+E0h] [rbp-20h] BYREF

  ValueName.Buffer = L"LastIndexValue";
  KeyHandle = 0;
  v20.Buffer = (PWSTR)&v26;
  *(_QWORD *)&ValueName.Length = 1966108;
  v19.Buffer = (PWSTR)&v27;
  v18 = 0;
  v25 = &v28;
  *(_QWORD *)&v20.Length = 0x100000;
  *(_QWORD *)&v19.Length = 0x100000;
  v24 = 3145728;
  *(_OWORD *)P = 0;
  *(_OWORD *)v22 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_ZDcc(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      (unsigned int)WPP_ff5744e1daca33e6b91278fb9c763f73_Traceguids,
      (_DWORD)a1,
      *a4,
      89,
      89);
  v8 = CscRebootRenamepOpenKey(&KeyHandle, a1, 0, 0);
  if ( v8 >= 0 )
  {
    v10 = 1;
    *a4 = 0;
    ExAcquireResourceExclusiveLite(Resource, 1u);
    IndexString = CscRegistrypReadULong(KeyHandle, &ValueName);
    if ( IndexString >= 0 )
    {
      v11 = 0;
      while ( 1 )
      {
        v12 = *a4;
        if ( (unsigned int)v12 >= v18 )
          break;
        IndexString = CscRebootRenamepGetIndexString(v12, &v20);
        if ( IndexString < 0 )
        {
          v11 = 438;
          break;
        }
        v13 = CscRegistrypReadString(KeyHandle, &v20);
        IndexString = v13;
        if ( v13 == -1073741772 )
        {
          IndexString = 0;
          *a4 += 2;
        }
        else
        {
          if ( v13 < 0 )
          {
            v11 = 464;
            break;
          }
          IndexString = CscRebootRenamepGetIndexString(*a4 + 1, &v19);
          if ( IndexString < 0 )
          {
            v11 = 467;
            break;
          }
          IndexString = CscRegistrypReadString(KeyHandle, &v19);
          if ( IndexString < 0 )
          {
            v11 = 472;
            break;
          }
          IndexString = CscRebootRenamepPerformRenameCallback(
                          *a4,
                          (_DWORD)KeyHandle,
                          a3,
                          (unsigned int)&v20,
                          (__int64)P,
                          (__int64)&v19,
                          (__int64)v22);
          if ( IndexString < 0 )
          {
            v11 = 494;
            break;
          }
          v14 = P[1];
          *a4 += 2;
          ExFreePoolWithTag(v14, 0);
          *(_OWORD *)P = 0;
          ExFreePoolWithTag(v22[1], 0);
          *(_OWORD *)v22 = 0;
        }
      }
    }
    else
    {
      v11 = 430;
    }
  }
  else
  {
    IndexString = 0;
    v10 = 0;
    v11 = 405;
    if ( v8 != -1073741772 )
      IndexString = v8;
  }
  v15 = KeyHandle;
  if ( KeyHandle )
  {
    if ( IndexString >= 0 )
    {
      ZwDeleteKey(KeyHandle);
      v15 = KeyHandle;
    }
    ZwClose(v15);
  }
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0);
    P[1] = 0;
  }
  if ( v22[1] )
  {
    ExFreePoolWithTag(v22[1], 0);
    v22[1] = 0;
  }
  if ( v10 )
    ExReleaseResourceLite(Resource);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_ff5744e1daca33e6b91278fb9c763f73_Traceguids,
      (unsigned int)IndexString,
      v11);
  return (unsigned int)IndexString;
}

```

## disassembly

```asm
0x1400529f8  push    rbp
0x1400529fa  push    rbx
0x1400529fb  push    rsi
0x1400529fc  push    rdi
0x1400529fd  push    r12
0x1400529ff  push    r14
0x140052a01  push    r15
0x140052a03  lea     rbp, [rsp-20h]
0x140052a08  sub     rsp, 120h
0x140052a0f  mov     rax, cs:__security_cookie
0x140052a16  xor     rax, rsp
0x140052a19  mov     [rbp+50h+var_40], rax
0x140052a1d  mov     r15, [rbp+50h+Resource]
0x140052a24  lea     rax, aLastindexvalue; "LastIndexValue"
0x140052a2b  mov     [rbp+50h+ValueName.Buffer], rax
0x140052a2f  xorps   xmm0, xmm0
0x140052a32  lea     rax, [rbp+50h+var_90]
0x140052a36  mov     [rsp+150h+KeyHandle], 0
0x140052a3f  mov     [rsp+150h+var_E0.Buffer], rax
0x140052a44  xorps   xmm1, xmm1
0x140052a47  lea     rax, [rbp+50h+var_80]
0x140052a4b  mov     qword ptr [rbp+50h+ValueName.Length], 1E001Ch
0x140052a53  mov     [rsp+150h+var_F0.Buffer], rax
0x140052a58  mov     rsi, r9
0x140052a5b  lea     rax, [rbp+50h+var_70]
0x140052a5f  mov     [rsp+150h+var_F8], 0
0x140052a67  mov     [rbp+50h+var_98], rax
0x140052a6b  mov     r12, r8
0x140052a6e  mov     rbx, rcx
0x140052a71  mov     qword ptr [rsp+150h+var_E0.Length], 100000h
0x140052a7a  mov     qword ptr [rsp+150h+var_F0.Length], 100000h
0x140052a83  mov     [rbp+50h+var_A0], 300000h
0x140052a8b  movups  xmmword ptr [rbp+50h+P], xmm0
0x140052a8f  movups  xmmword ptr [rbp+50h+var_C0], xmm1
0x140052a93  mov     rcx, cs:WPP_GLOBAL_Control
0x140052a9a  lea     rax, WPP_GLOBAL_Control
0x140052aa1  cmp     rcx, rax
0x140052aa4  jz      short loc_140052AD6
0x140052aa6  mov     eax, [rcx+2Ch]
0x140052aa9  test    al, 20h
0x140052aab  jz      short loc_140052AD6
0x140052aad  mov     eax, [r9]
0x140052ab0  lea     r8, WPP_ff5744e1daca33e6b91278fb9c763f73_Traceguids
0x140052ab7  mov     rcx, [rcx+18h]
0x140052abb  mov     r9, rbx
0x140052abe  mov     byte ptr [rsp+150h+var_120], 59h ; 'Y'
0x140052ac3  mov     edx, 0Ch
0x140052ac8  mov     byte ptr [rsp+150h+var_128], 59h ; 'Y'
0x140052acd  mov     dword ptr [rsp+150h+var_130], eax
0x140052ad1  call    WPP_SF_ZDcc
0x140052ad6  xor     r9d, r9d
0x140052ad9  lea     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x140052ade  xor     r8d, r8d
0x140052ae1  mov     rdx, rbx
0x140052ae4  call    CscRebootRenamepOpenKey
0x140052ae9  test    eax, eax
0x140052aeb  jns     short loc_140052B04
0x140052aed  xor     ebx, ebx
0x140052aef  xor     r14b, r14b
0x140052af2  cmp     eax, 0C0000034h
0x140052af7  mov     edi, 195h
0x140052afc  cmovnz  ebx, eax
0x140052aff  jmp     loc_140052C66
0x140052b04  mov     r14d, 1
0x140052b0a  mov     dword ptr [rsi], 0
0x140052b10  mov     dl, r14b; Wait
0x140052b13  mov     rcx, r15; Resource
0x140052b16  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140052b1d  nop     dword ptr [rax+rax+00h]
0x140052b22  mov     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x140052b27  lea     r8, [rsp+150h+var_F8]
0x140052b2c  lea     rdx, [rbp+50h+ValueName]; ValueName
0x140052b30  call    CscRegistrypReadULong
0x140052b35  mov     ebx, eax
0x140052b37  test    eax, eax
0x140052b39  jns     short loc_140052B45
0x140052b3b  mov     edi, 1AEh
0x140052b40  jmp     loc_140052C66
0x140052b45  xor     edi, edi
0x140052b47  mov     ecx, [rsi]
0x140052b49  cmp     ecx, [rsp+150h+var_F8]
0x140052b4d  jnb     loc_140052C66
0x140052b53  lea     rdx, [rsp+150h+var_E0]
0x140052b58  call    CscRebootRenamepGetIndexString
0x140052b5d  mov     ebx, eax
0x140052b5f  test    eax, eax
0x140052b61  js      loc_140052C61
0x140052b67  mov     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x140052b6c  lea     r8, [rbp+50h+P]
0x140052b70  lea     rdx, [rsp+150h+var_E0]; ValueName
0x140052b75  call    CscRegistrypReadString
0x140052b7a  mov     ebx, eax
0x140052b7c  cmp     eax, 0C0000034h
0x140052b81  jnz     short loc_140052B8A
0x140052b83  xor     ebx, ebx
0x140052b85  add     dword ptr [rsi], 2
0x140052b88  jmp     short loc_140052B47
0x140052b8a  test    eax, eax
0x140052b8c  js      loc_140052C5A
0x140052b92  mov     ecx, [rsi]
0x140052b94  lea     rdx, [rsp+150h+var_F0]
0x140052b99  add     ecx, r14d
0x140052b9c  call    CscRebootRenamepGetIndexString
0x140052ba1  mov     ebx, eax
0x140052ba3  test    eax, eax
0x140052ba5  js      loc_140052C53
0x140052bab  mov     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x140052bb0  lea     r8, [rbp+50h+var_C0]
0x140052bb4  lea     rdx, [rsp+150h+var_F0]; ValueName
0x140052bb9  call    CscRegistrypReadString
0x140052bbe  mov     ebx, eax
0x140052bc0  test    eax, eax
0x140052bc2  js      loc_140052C4C
0x140052bc8  mov     rdx, [rsp+150h+KeyHandle]
0x140052bcd  lea     rax, [rbp+50h+var_C0]
0x140052bd1  mov     ecx, [rsi]
0x140052bd3  lea     r9, [rsp+150h+var_E0]
0x140052bd8  mov     [rsp+150h+var_110], 0C000000Dh
0x140052be0  mov     r8, r12
0x140052be3  mov     [rsp+150h+var_118], rdi
0x140052be8  mov     [rsp+150h+var_120], rax
0x140052bed  lea     rax, [rsp+150h+var_F0]
0x140052bf2  mov     [rsp+150h+var_128], rax
0x140052bf7  lea     rax, [rbp+50h+P]
0x140052bfb  mov     [rsp+150h+var_130], rax
0x140052c00  call    CscRebootRenamepPerformRenameCallback
0x140052c05  mov     ebx, eax
0x140052c07  test    eax, eax
0x140052c09  js      short loc_140052C45
0x140052c0b  mov     rcx, [rbp+50h+P+8]; P
0x140052c0f  xor     edx, edx; Tag
0x140052c11  add     dword ptr [rsi], 2
0x140052c14  call    cs:__imp_ExFreePoolWithTag
0x140052c1b  nop     dword ptr [rax+rax+00h]
0x140052c20  mov     rcx, [rbp+50h+var_C0+8]; P
0x140052c24  xorps   xmm0, xmm0
0x140052c27  xor     edx, edx; Tag
0x140052c29  movups  xmmword ptr [rbp+50h+P], xmm0
0x140052c2d  call    cs:__imp_ExFreePoolWithTag
0x140052c34  nop     dword ptr [rax+rax+00h]
0x140052c39  xorps   xmm0, xmm0
0x140052c3c  movups  xmmword ptr [rbp+50h+var_C0], xmm0
0x140052c40  jmp     loc_140052B47
0x140052c45  mov     edi, 1EEh
0x140052c4a  jmp     short loc_140052C66
0x140052c4c  mov     edi, 1D8h
0x140052c51  jmp     short loc_140052C66
0x140052c53  mov     edi, 1D3h
0x140052c58  jmp     short loc_140052C66
0x140052c5a  mov     edi, 1D0h
0x140052c5f  jmp     short loc_140052C66
0x140052c61  mov     edi, 1B6h
0x140052c66  mov     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x140052c6b  test    rcx, rcx
0x140052c6e  jz      short loc_140052C91
0x140052c70  test    ebx, ebx
0x140052c72  js      short loc_140052C85
0x140052c74  call    cs:__imp_ZwDeleteKey
0x140052c7b  nop     dword ptr [rax+rax+00h]
0x140052c80  mov     rcx, [rsp+150h+KeyHandle]; Handle
0x140052c85  call    cs:__imp_ZwClose
0x140052c8c  nop     dword ptr [rax+rax+00h]
0x140052c91  mov     rcx, [rbp+50h+P+8]; P
0x140052c95  test    rcx, rcx
0x140052c98  jz      short loc_140052CB0
0x140052c9a  xor     edx, edx; Tag
0x140052c9c  call    cs:__imp_ExFreePoolWithTag
0x140052ca3  nop     dword ptr [rax+rax+00h]
0x140052ca8  mov     [rbp+50h+P+8], 0
0x140052cb0  mov     rcx, [rbp+50h+var_C0+8]; P
0x140052cb4  test    rcx, rcx
0x140052cb7  jz      short loc_140052CCF
0x140052cb9  xor     edx, edx; Tag
0x140052cbb  call    cs:__imp_ExFreePoolWithTag
0x140052cc2  nop     dword ptr [rax+rax+00h]
0x140052cc7  mov     [rbp+50h+var_C0+8], 0
0x140052ccf  test    r14b, r14b
0x140052cd2  jz      short loc_140052CE3
0x140052cd4  mov     rcx, r15; Resource
0x140052cd7  call    cs:__imp_ExReleaseResourceLite
0x140052cde  nop     dword ptr [rax+rax+00h]
0x140052ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x140052cea  lea     rax, WPP_GLOBAL_Control
0x140052cf1  cmp     rcx, rax
0x140052cf4  jz      short loc_140052D19
0x140052cf6  mov     eax, [rcx+2Ch]
0x140052cf9  test    al, 20h
0x140052cfb  jz      short loc_140052D19
0x140052cfd  mov     rcx, [rcx+18h]
0x140052d01  lea     r8, WPP_ff5744e1daca33e6b91278fb9c763f73_Traceguids
0x140052d08  mov     edx, 0Dh
0x140052d0d  mov     dword ptr [rsp+150h+var_130], edi
0x140052d11  mov     r9d, ebx
0x140052d14  call    WPP_SF_Dd
0x140052d19  mov     eax, ebx
0x140052d1b  mov     rcx, [rbp+50h+var_40]
0x140052d1f  xor     rcx, rsp; StackCookie
0x140052d22  call    __security_check_cookie
0x140052d27  add     rsp, 120h
0x140052d2e  pop     r15
0x140052d30  pop     r14
0x140052d32  pop     r12
0x140052d34  pop     rdi
0x140052d35  pop     rsi
0x140052d36  pop     rbx
0x140052d37  pop     rbp
0x140052d38  retn
```
