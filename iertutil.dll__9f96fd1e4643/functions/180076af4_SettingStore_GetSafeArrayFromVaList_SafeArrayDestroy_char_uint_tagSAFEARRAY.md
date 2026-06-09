# SettingStore::_GetSafeArrayFromVaList_SafeArrayDestroy(char *,uint,tagSAFEARRAY * *)

- ea: `0x180076af4`
- end: `0x180076bd5`
- name: `?_GetSafeArrayFromVaList_SafeArrayDestroy@SettingStore@@YAJPEADIPEAPEAUtagSAFEARRAY@@@Z`
- size: `225`
- prototype: `int(SettingStore *__hidden this, char *, unsigned int, struct tagSAFEARRAY **)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180075c28`
- `0x180075e5c`
- `0x18007649c`

## callees

- `0x180076af4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180076b5f`
- `OLEAUT32!__imp_SysAllocString` at `0x180076b5f`
- `OLEAUT32!__imp_SysFreeString` at `0x180076b87`
- `OLEAUT32!__imp_SysFreeString` at `0x180076b87`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180076ba8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180076ba8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180076b43`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180076b43`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180076b96`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180076b96`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180076b24`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180076b24`

## pseudocode

```c
__int64 __fastcall SettingStore::_GetSafeArrayFromVaList_SafeArrayDestroy(
        const OLECHAR **this,
        char *a2,
        SAFEARRAY **a3,
        struct tagSAFEARRAY **a4)
{
  unsigned int v5; // ebp
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v8; // rdi
  HRESULT i; // ebx
  BSTR *v10; // r12
  __int64 v11; // rsi
  BSTR v12; // rax
  __int64 v13; // rbp
  void *ppvData; // [rsp+68h] [rbp+20h] BYREF

  v5 = (unsigned int)a2;
  if ( (_DWORD)a2 )
  {
    Vector = SafeArrayCreateVector(8u, 0, (ULONG)a2);
    v8 = Vector;
    if ( Vector )
    {
      ppvData = 0;
      i = SafeArrayAccessData(Vector, &ppvData);
      if ( i < 0 )
        goto LABEL_12;
      v10 = (BSTR *)ppvData;
      i = 0;
      v11 = 0;
      while ( (unsigned int)v11 < v5 )
      {
        v12 = SysAllocString(*this);
        if ( !v12 )
        {
          v13 = 0;
          for ( i = -2147024882; (unsigned int)v13 < (unsigned int)v11; v13 = (unsigned int)(v13 + 1) )
            SysFreeString(v10[v13]);
          break;
        }
        v10[v11] = v12;
        ++this;
        v11 = (unsigned int)(v11 + 1);
        i = 0;
      }
      SafeArrayUnaccessData(v8);
      if ( i < 0 )
LABEL_12:
        SafeArrayDestroy(v8);
      else
        *a3 = v8;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180076af4  mov     [rsp+arg_0], rbx
0x180076af9  mov     [rsp+arg_8], rbp
0x180076afe  push    rsi
0x180076aff  push    rdi
0x180076b00  push    r12
0x180076b02  push    r14
0x180076b04  push    r15
0x180076b06  sub     rsp, 20h
0x180076b0a  mov     r15, r8
0x180076b0d  mov     ebp, edx
0x180076b0f  mov     r14, rcx
0x180076b12  test    edx, edx
0x180076b14  jz      loc_180076BB7
0x180076b1a  mov     r8d, edx; cElements
0x180076b1d  mov     ecx, 8; vt
0x180076b22  xor     edx, edx; lLbound
0x180076b24  call    cs:__imp_SafeArrayCreateVector
0x180076b2a  mov     rdi, rax
0x180076b2d  test    rax, rax
0x180076b30  jz      short loc_180076BB0
0x180076b32  lea     rdx, [rsp+48h+ppvData]; ppvData
0x180076b37  mov     [rsp+48h+ppvData], 0
0x180076b40  mov     rcx, rax; psa
0x180076b43  call    cs:__imp_SafeArrayAccessData
0x180076b49  mov     ebx, eax
0x180076b4b  test    eax, eax
0x180076b4d  js      short loc_180076BA5
0x180076b4f  mov     r12, [rsp+48h+ppvData]
0x180076b54  xor     ebx, ebx
0x180076b56  xor     esi, esi
0x180076b58  cmp     esi, ebp
0x180076b5a  jnb     short loc_180076B93
0x180076b5c  mov     rcx, [r14]; psz
0x180076b5f  call    cs:__imp_SysAllocString
0x180076b65  test    rax, rax
0x180076b68  jz      short loc_180076B78
0x180076b6a  mov     [r12+rsi*8], rax
0x180076b6e  add     r14, 8
0x180076b72  inc     esi
0x180076b74  xor     ebx, ebx
0x180076b76  jmp     short loc_180076B58
0x180076b78  xor     ebp, ebp
0x180076b7a  mov     ebx, 8007000Eh
0x180076b7f  test    esi, esi
0x180076b81  jz      short loc_180076B93
0x180076b83  mov     rcx, [r12+rbp*8]; bstrString
0x180076b87  call    cs:__imp_SysFreeString
0x180076b8d  inc     ebp
0x180076b8f  cmp     ebp, esi
0x180076b91  jb      short loc_180076B83
0x180076b93  mov     rcx, rdi; psa
0x180076b96  call    cs:__imp_SafeArrayUnaccessData
0x180076b9c  test    ebx, ebx
0x180076b9e  js      short loc_180076BA5
0x180076ba0  mov     [r15], rdi
0x180076ba3  jmp     short loc_180076BBC
0x180076ba5  mov     rcx, rdi; psa
0x180076ba8  call    cs:__imp_SafeArrayDestroy
0x180076bae  jmp     short loc_180076BBC
0x180076bb0  mov     ebx, 8007000Eh
0x180076bb5  jmp     short loc_180076BBC
0x180076bb7  mov     ebx, 80070057h
0x180076bbc  mov     rbp, [rsp+48h+arg_8]
0x180076bc1  mov     eax, ebx
0x180076bc3  mov     rbx, [rsp+48h+arg_0]
0x180076bc8  add     rsp, 20h
0x180076bcc  pop     r15
0x180076bce  pop     r14
0x180076bd0  pop     r12
0x180076bd2  pop     rdi
0x180076bd3  pop     rsi
0x180076bd4  retn
```
