# PnpApiWrapper::Details::OnDeviceNotification(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)

- ea: `0x180085ad0`
- end: `0x180085c58`
- name: `?OnDeviceNotification@Details@PnpApiWrapper@@YAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z`
- size: `392`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18002deb8`
- `0x180085ad0`
- `0x18008e2b4`
- `0x1800f0990`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180085c04`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180085c04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085b93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085bd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085b93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085bd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PnpApiWrapper::Details::OnDeviceNotification(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        unsigned int a5)
{
  const wchar_t *v6; // rdi
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  unsigned int v12; // ebx
  int v13; // r8d
  int v14; // r8d
  PnpDevice *v15; // rsi
  unsigned __int64 v16; // rsi
  unsigned int v17; // eax
  HSTRING string; // [rsp+20h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-40h] BYREF
  __int64 v21; // [rsp+40h] [rbp-28h]

  if ( !a2 || *(_QWORD *)a2 != a1 )
    return 0;
  v6 = 0;
  if ( !a3 )
  {
    v12 = 3;
    goto LABEL_24;
  }
  v7 = a3 - 1;
  if ( !v7 )
  {
    v12 = 4;
LABEL_24:
    v6 = (const wchar_t *)(a4 + 24);
    goto LABEL_25;
  }
  v8 = v7 - 1;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = 2;
          v13 = v11 - 2;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              if ( v14 != 1 )
                return 0;
            }
            else
            {
              v12 = 1;
            }
          }
          else
          {
            v12 = 0;
          }
          v6 = (const wchar_t *)(a4 + 8);
          goto LABEL_25;
        }
        v12 = 8;
      }
      else
      {
        v12 = 7;
      }
    }
    else
    {
      v12 = 6;
    }
  }
  else
  {
    v12 = 5;
  }
  v15 = *(PnpDevice **)(a2 + 16);
  if ( !v15 )
  {
LABEL_25:
    v16 = (a4 + a5 - (unsigned __int64)v6) >> 1;
    if ( v16 <= 0xFFFFFFFF )
    {
      v17 = wcsnlen(v6, (a4 + a5 - (unsigned __int64)v6) >> 1);
      if ( v17 )
      {
        if ( v17 < v16 )
        {
          Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v6, v17);
          try
          {
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(a2 + 8))(v12, v21, *(_QWORD *)(a2 + 16));
          }
          catch ( ... )
          {
            return 0;
          }
        }
      }
    }
    return 0;
  }
  WindowsDeleteString(0);
  string = 0;
  if ( (int)PnpDevice::GetInterfacePath(v15, &string) >= 0 )
  {
    try
    {
      (*(void (__fastcall **)(_QWORD, HSTRING, _QWORD))(a2 + 8))(v12, string, *((_QWORD *)v15 + 18));
    }
    catch ( ... )
    {
    }
  }
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x180085ad0  mov     [rsp+arg_0], rbx
0x180085ad5  push    rsi
0x180085ad6  push    rdi
0x180085ad7  push    r14
0x180085ad9  sub     rsp, 50h
0x180085add  mov     rax, cs:__security_cookie
0x180085ae4  xor     rax, rsp
0x180085ae7  mov     [rsp+68h+var_20], rax
0x180085aec  mov     r14, rdx
0x180085aef  mov     edx, [rsp+68h+arg_20]
0x180085af6  test    r14, r14
0x180085af9  jz      loc_180085C3B
0x180085aff  cmp     [r14], rcx
0x180085b02  jnz     loc_180085C3B
0x180085b08  xor     edi, edi
0x180085b0a  test    r8d, r8d
0x180085b0d  jz      loc_180085BDF
0x180085b13  sub     r8d, 1
0x180085b17  jz      loc_180085BD8
0x180085b1d  sub     r8d, 1
0x180085b21  jz      short loc_180085B76
0x180085b23  sub     r8d, 1
0x180085b27  jz      short loc_180085B6F
0x180085b29  sub     r8d, 1
0x180085b2d  jz      short loc_180085B68
0x180085b2f  sub     r8d, 1
0x180085b33  jz      short loc_180085B61
0x180085b35  lea     ebx, [rdi+2]
0x180085b38  sub     r8d, ebx
0x180085b3b  jz      short loc_180085B5D
0x180085b3d  sub     r8d, 1
0x180085b41  jz      short loc_180085B56
0x180085b43  cmp     r8d, 1
0x180085b47  jnz     loc_180085C3B
0x180085b4d  lea     rdi, [r9+8]
0x180085b51  jmp     loc_180085BE8
0x180085b56  mov     ebx, 1
0x180085b5b  jmp     short loc_180085B4D
0x180085b5d  xor     ebx, ebx
0x180085b5f  jmp     short loc_180085B4D
0x180085b61  mov     ebx, 8
0x180085b66  jmp     short loc_180085B7B
0x180085b68  mov     ebx, 7
0x180085b6d  jmp     short loc_180085B7B
0x180085b6f  mov     ebx, 6
0x180085b74  jmp     short loc_180085B7B
0x180085b76  mov     ebx, 5
0x180085b7b  mov     eax, 10h
0x180085b80  mov     rcx, r14
0x180085b83  mov     rsi, [rcx+rax]
0x180085b87  test    rsi, rsi
0x180085b8a  jz      short loc_180085BE8
0x180085b8c  mov     [rsp+68h+string], rdi
0x180085b91  xor     ecx, ecx; string
0x180085b93  call    cs:__imp_WindowsDeleteString
0x180085b99  mov     [rsp+68h+string], 0
0x180085ba2  lea     rdx, [rsp+68h+string]; HSTRING *
0x180085ba7  mov     rcx, rsi; this
0x180085baa  call    ?GetInterfacePath@PnpDevice@@QEAAJPEAPEAUHSTRING__@@@Z; PnpDevice::GetInterfacePath(HSTRING__ * *)
0x180085baf  test    eax, eax
0x180085bb1  js      short loc_180085BCB
0x180085bb3  mov     r8, [rsi+90h]
0x180085bba  mov     rdx, [rsp+68h+string]
0x180085bbf  mov     ecx, ebx
0x180085bc1  mov     rax, [r14+8]
0x180085bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085bca  nop
0x180085bcb  mov     rcx, [rsp+68h+string]; string
0x180085bd0  call    cs:__imp_WindowsDeleteString
0x180085bd6  jmp     short loc_180085C3B
0x180085bd8  mov     ebx, 4
0x180085bdd  jmp     short loc_180085BE4
0x180085bdf  mov     ebx, 3
0x180085be4  lea     rdi, [r9+18h]
0x180085be8  mov     rsi, rdx
0x180085beb  sub     rsi, rdi
0x180085bee  add     rsi, r9
0x180085bf1  shr     rsi, 1
0x180085bf4  mov     eax, 0FFFFFFFFh
0x180085bf9  cmp     rsi, rax
0x180085bfc  ja      short loc_180085C3B
0x180085bfe  mov     rdx, rsi; MaxCount
0x180085c01  mov     rcx, rdi; Source
0x180085c04  call    cs:__imp_wcsnlen
0x180085c0a  test    eax, eax
0x180085c0c  jz      short loc_180085C3B
0x180085c0e  mov     ecx, eax
0x180085c10  cmp     rcx, rsi
0x180085c13  jnb     short loc_180085C3B
0x180085c15  mov     r8d, eax; unsigned int
0x180085c18  mov     rdx, rdi; sourceString
0x180085c1b  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x180085c20  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@PEBGI@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const *,uint)
0x180085c25  nop
0x180085c26  mov     r8, [r14+10h]
0x180085c2a  mov     rdx, [rsp+68h+var_28]
0x180085c2f  mov     ecx, ebx
0x180085c31  mov     rax, [r14+8]
0x180085c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c3a  nop
0x180085c3b  xor     eax, eax
0x180085c3d  mov     rcx, [rsp+68h+var_20]
0x180085c42  xor     rcx, rsp; StackCookie
0x180085c45  call    __security_check_cookie
0x180085c4a  mov     rbx, [rsp+68h+arg_0]
0x180085c4f  add     rsp, 50h
0x180085c53  pop     r14
0x180085c55  pop     rdi
0x180085c56  pop     rsi
0x180085c57  retn
```
