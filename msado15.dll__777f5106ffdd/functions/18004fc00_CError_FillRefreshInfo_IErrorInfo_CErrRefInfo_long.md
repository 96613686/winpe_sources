# CError::FillRefreshInfo(IErrorInfo *,CErrRefInfo *,long)

- ea: `0x18004fc00`
- end: `0x18004fe87`
- name: `?FillRefreshInfo@CError@@UEAAJPEAUIErrorInfo@@PEAVCErrRefInfo@@J@Z`
- size: `647`
- prototype: `__int64 __fastcall(CError *__hidden this, struct IErrorInfo *, struct CErrRefInfo *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18004fc00`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18004fc2f`
- `KERNEL32!GetCurrentThreadId` at `0x18004fc2f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004fd4e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004fdef`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004fe2e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004fd4e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004fdef`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004fe2e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fd19`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fd8e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fdc1`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fe54`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fe65`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fe76`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fd19`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fd8e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fdc1`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fe54`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fe65`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fe76`
- `OLEAUT32!__imp_SysStringLen` at `0x18004fd3d`
- `OLEAUT32!__imp_SysStringLen` at `0x18004fdde`
- `OLEAUT32!__imp_SysStringLen` at `0x18004fe1d`
- `OLEAUT32!__imp_SysStringLen` at `0x18004fd3d`
- `OLEAUT32!__imp_SysStringLen` at `0x18004fdde`
- `OLEAUT32!__imp_SysStringLen` at `0x18004fe1d`

## pseudocode

```c
__int64 __fastcall CError::FillRefreshInfo(CError *this, struct IErrorInfo *a2, struct CErrRefInfo *a3, int a4)
{
  unsigned int v6; // ebx
  char v8; // al
  const OLECHAR *v9; // rsi
  UINT v10; // eax
  char v11; // al
  const OLECHAR *v12; // rbx
  char v13; // al
  const OLECHAR *v14; // rsi
  UINT v15; // eax
  UINT v16; // eax
  BSTR bstrString[2]; // [rsp+20h] [rbp-28h] BYREF
  BSTR pbstr; // [rsp+58h] [rbp+10h] BYREF
  BSTR strIn; // [rsp+60h] [rbp+18h] BYREF

  pbstr = 0;
  strIn = 0;
  bstrString[0] = 0;
  *(_DWORD *)a3 = a4;
  *((_DWORD *)a3 + 2) = GetCurrentThreadId();
  ((void (__fastcall *)(struct IErrorInfo *, char *))a2->lpVtbl->GetHelpContext)(a2, (char *)a3 + 12);
  if ( ((int (__fastcall *)(struct IErrorInfo *, BSTR *))a2->lpVtbl->GetDescription)(a2, &pbstr) >= 0 )
  {
    v8 = *((_BYTE *)a3 + 24);
    v9 = pbstr;
    if ( (v8 & 1) != 0
      && pbstr
      && (v10 = SysStringLen(pbstr), v9 = SysAllocStringLen(v9, v10), v8 = *((_BYTE *)a3 + 24), !v9) )
    {
      *((_BYTE *)a3 + 24) = v8 & 0xFB;
    }
    else
    {
      *((_BYTE *)a3 + 24) = v8 | 4;
      if ( (v8 & 2) != 0 )
        SysFreeString(*((BSTR *)a3 + 2));
      *((_QWORD *)a3 + 2) = v9;
    }
  }
  if ( ((int (__fastcall *)(struct IErrorInfo *, BSTR *))a2->lpVtbl->GetHelpFile)(a2, bstrString) >= 0 )
  {
    v13 = *((_BYTE *)a3 + 56);
    v14 = bstrString[0];
    if ( (v13 & 1) != 0
      && bstrString[0]
      && (v16 = SysStringLen(bstrString[0]), v14 = SysAllocStringLen(v14, v16), v13 = *((_BYTE *)a3 + 56), !v14) )
    {
      *((_BYTE *)a3 + 56) = v13 & 0xFB;
    }
    else
    {
      *((_BYTE *)a3 + 56) = v13 | 4;
      if ( (v13 & 2) != 0 )
        SysFreeString(*((BSTR *)a3 + 6));
      *((_QWORD *)a3 + 6) = v14;
    }
  }
  if ( ((int (__fastcall *)(struct IErrorInfo *, BSTR *))a2->lpVtbl->GetSource)(a2, &strIn) >= 0 )
  {
    v11 = *((_BYTE *)a3 + 40);
    v12 = strIn;
    if ( (v11 & 1) != 0
      && strIn
      && (v15 = SysStringLen(strIn), v12 = SysAllocStringLen(v12, v15), v11 = *((_BYTE *)a3 + 40), !v12) )
    {
      *((_BYTE *)a3 + 40) = v11 & 0xFB;
    }
    else
    {
      *((_BYTE *)a3 + 40) = v11 | 4;
      if ( (v11 & 2) != 0 )
        SysFreeString(*((BSTR *)a3 + 4));
      *((_QWORD *)a3 + 4) = v12;
    }
  }
  if ( (*((_BYTE *)a3 + 24) & 4) == 0 || (*((_BYTE *)a3 + 40) & 4) == 0 || (v6 = 0, (*((_BYTE *)a3 + 56) & 4) == 0) )
    v6 = -2147024882;
  if ( pbstr )
    SysFreeString(pbstr);
  if ( strIn )
    SysFreeString(strIn);
  if ( bstrString[0] )
    SysFreeString(bstrString[0]);
  return v6;
}

```

## disassembly

```asm
0x18004fc00  push    rbx
0x18004fc02  sub     rsp, 40h
0x18004fc06  mov     [rsp+48h+arg_0], rbp
0x18004fc0b  mov     rbx, rdx
0x18004fc0e  xor     ebp, ebp
0x18004fc10  mov     [rsp+48h+var_10], rsi
0x18004fc15  mov     [rsp+48h+var_18], rdi
0x18004fc1a  mov     rdi, r8
0x18004fc1d  mov     [rsp+48h+pbstr], rbp
0x18004fc22  mov     [rsp+48h+strIn], rbp
0x18004fc27  mov     [rsp+48h+bstrString], rbp
0x18004fc2c  mov     [r8], r9d
0x18004fc2f  call    cs:__imp_GetCurrentThreadId
0x18004fc36  nop     dword ptr [rax+rax+00h]
0x18004fc3b  mov     [rdi+8], eax
0x18004fc3e  lea     rdx, [rdi+0Ch]
0x18004fc42  mov     rax, [rbx]
0x18004fc45  mov     rcx, rbx
0x18004fc48  mov     rax, [rax+38h]
0x18004fc4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc51  mov     rax, [rbx]
0x18004fc54  lea     rdx, [rsp+48h+pbstr]
0x18004fc59  mov     rcx, rbx
0x18004fc5c  mov     rax, [rax+28h]
0x18004fc60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc65  test    eax, eax
0x18004fc67  jns     loc_18004FCFB
0x18004fc6d  mov     rax, [rbx]
0x18004fc70  lea     rdx, [rsp+48h+bstrString]
0x18004fc75  mov     rcx, rbx
0x18004fc78  mov     rax, [rax+30h]
0x18004fc7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc81  test    eax, eax
0x18004fc83  jns     loc_18004FDA3
0x18004fc89  mov     rax, [rbx]
0x18004fc8c  lea     rdx, [rsp+48h+strIn]
0x18004fc91  mov     rcx, rbx
0x18004fc94  mov     rax, [rax+20h]
0x18004fc98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc9d  mov     rsi, [rsp+48h+var_10]
0x18004fca2  test    eax, eax
0x18004fca4  jns     loc_18004FD70
0x18004fcaa  test    byte ptr [rdi+18h], 4
0x18004fcae  jz      short loc_18004FD2E
0x18004fcb0  test    byte ptr [rdi+28h], 4
0x18004fcb4  jz      short loc_18004FD2E
0x18004fcb6  test    byte ptr [rdi+38h], 4
0x18004fcba  mov     ebx, ebp
0x18004fcbc  jz      short loc_18004FD2E
0x18004fcbe  mov     rcx, [rsp+48h+pbstr]; bstrString
0x18004fcc3  mov     rdi, [rsp+48h+var_18]
0x18004fcc8  mov     rbp, [rsp+48h+arg_0]
0x18004fccd  test    rcx, rcx
0x18004fcd0  jnz     loc_18004FE54
0x18004fcd6  mov     rcx, [rsp+48h+strIn]; bstrString
0x18004fcdb  test    rcx, rcx
0x18004fcde  jnz     loc_18004FE65
0x18004fce4  mov     rcx, [rsp+48h+bstrString]; bstrString
0x18004fce9  test    rcx, rcx
0x18004fcec  jnz     loc_18004FE76
0x18004fcf2  mov     eax, ebx
0x18004fcf4  add     rsp, 40h
0x18004fcf8  pop     rbx
0x18004fcf9  retn
0x18004fcfb  movzx   eax, byte ptr [rdi+18h]
0x18004fcff  mov     rsi, [rsp+48h+pbstr]
0x18004fd04  test    al, 1
0x18004fd06  jnz     short loc_18004FD35
0x18004fd08  movzx   ecx, al
0x18004fd0b  or      al, 4
0x18004fd0d  mov     [rdi+18h], al
0x18004fd10  test    cl, 2
0x18004fd13  jz      short loc_18004FD25
0x18004fd15  mov     rcx, [rdi+10h]; bstrString
0x18004fd19  call    cs:__imp_SysFreeString
0x18004fd20  nop     dword ptr [rax+rax+00h]
0x18004fd25  mov     [rdi+10h], rsi
0x18004fd29  jmp     loc_18004FC6D
0x18004fd2e  mov     ebx, 8007000Eh
0x18004fd33  jmp     short loc_18004FCBE
0x18004fd35  test    rsi, rsi
0x18004fd38  jz      short loc_18004FD08
0x18004fd3a  mov     rcx, rsi; pbstr
0x18004fd3d  call    cs:__imp_SysStringLen
0x18004fd44  nop     dword ptr [rax+rax+00h]
0x18004fd49  mov     edx, eax; ui
0x18004fd4b  mov     rcx, rsi; strIn
0x18004fd4e  call    cs:__imp_SysAllocStringLen
0x18004fd55  nop     dword ptr [rax+rax+00h]
0x18004fd5a  mov     rsi, rax
0x18004fd5d  movzx   eax, byte ptr [rdi+18h]
0x18004fd61  test    rsi, rsi
0x18004fd64  jnz     short loc_18004FD08
0x18004fd66  and     al, 0FBh
0x18004fd68  mov     [rdi+18h], al
0x18004fd6b  jmp     loc_18004FC6D
0x18004fd70  movzx   eax, byte ptr [rdi+28h]
0x18004fd74  mov     rbx, [rsp+48h+strIn]
0x18004fd79  test    al, 1
0x18004fd7b  jnz     short loc_18004FDD6
0x18004fd7d  movzx   ecx, al
0x18004fd80  or      al, 4
0x18004fd82  mov     [rdi+28h], al
0x18004fd85  test    cl, 2
0x18004fd88  jz      short loc_18004FD9A
0x18004fd8a  mov     rcx, [rdi+20h]; bstrString
0x18004fd8e  call    cs:__imp_SysFreeString
0x18004fd95  nop     dword ptr [rax+rax+00h]
0x18004fd9a  mov     [rdi+20h], rbx
0x18004fd9e  jmp     loc_18004FCAA
0x18004fda3  movzx   eax, byte ptr [rdi+38h]
0x18004fda7  mov     rsi, [rsp+48h+bstrString]
0x18004fdac  test    al, 1
0x18004fdae  jnz     short loc_18004FE15
0x18004fdb0  movzx   ecx, al
0x18004fdb3  or      al, 4
0x18004fdb5  mov     [rdi+38h], al
0x18004fdb8  test    cl, 2
0x18004fdbb  jz      short loc_18004FDCD
0x18004fdbd  mov     rcx, [rdi+30h]; bstrString
0x18004fdc1  call    cs:__imp_SysFreeString
0x18004fdc8  nop     dword ptr [rax+rax+00h]
0x18004fdcd  mov     [rdi+30h], rsi
0x18004fdd1  jmp     loc_18004FC89
0x18004fdd6  test    rbx, rbx
0x18004fdd9  jz      short loc_18004FD7D
0x18004fddb  mov     rcx, rbx; pbstr
0x18004fdde  call    cs:__imp_SysStringLen
0x18004fde5  nop     dword ptr [rax+rax+00h]
0x18004fdea  mov     edx, eax; ui
0x18004fdec  mov     rcx, rbx; strIn
0x18004fdef  call    cs:__imp_SysAllocStringLen
0x18004fdf6  nop     dword ptr [rax+rax+00h]
0x18004fdfb  mov     rbx, rax
0x18004fdfe  movzx   eax, byte ptr [rdi+28h]
0x18004fe02  test    rbx, rbx
0x18004fe05  jnz     loc_18004FD7D
0x18004fe0b  and     al, 0FBh
0x18004fe0d  mov     [rdi+28h], al
0x18004fe10  jmp     loc_18004FCAA
0x18004fe15  test    rsi, rsi
0x18004fe18  jz      short loc_18004FDB0
0x18004fe1a  mov     rcx, rsi; pbstr
0x18004fe1d  call    cs:__imp_SysStringLen
0x18004fe24  nop     dword ptr [rax+rax+00h]
0x18004fe29  mov     edx, eax; ui
0x18004fe2b  mov     rcx, rsi; strIn
0x18004fe2e  call    cs:__imp_SysAllocStringLen
0x18004fe35  nop     dword ptr [rax+rax+00h]
0x18004fe3a  mov     rsi, rax
0x18004fe3d  movzx   eax, byte ptr [rdi+38h]
0x18004fe41  test    rsi, rsi
0x18004fe44  jnz     loc_18004FDB0
0x18004fe4a  and     al, 0FBh
0x18004fe4c  mov     [rdi+38h], al
0x18004fe4f  jmp     loc_18004FC89
0x18004fe54  call    cs:__imp_SysFreeString
0x18004fe5b  nop     dword ptr [rax+rax+00h]
0x18004fe60  jmp     loc_18004FCD6
0x18004fe65  call    cs:__imp_SysFreeString
0x18004fe6c  nop     dword ptr [rax+rax+00h]
0x18004fe71  jmp     loc_18004FCE4
0x18004fe76  call    cs:__imp_SysFreeString
0x18004fe7d  nop     dword ptr [rax+rax+00h]
0x18004fe82  jmp     loc_18004FCF2
```
