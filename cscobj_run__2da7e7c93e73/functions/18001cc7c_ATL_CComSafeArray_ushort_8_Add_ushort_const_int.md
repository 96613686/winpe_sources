# ATL::CComSafeArray<ushort *,8>::Add(ushort * const &,int)

- ea: `0x18001cc7c`
- end: `0x18001cd9a`
- name: `?Add@?$CComSafeArray@PEAG$07@ATL@@QEAAJAEBQEAGH@Z`
- size: `286`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001ec30`
- `0x18001ef70`
- `0x18001f22c`

## callees

- `0x18001886c`
- `0x18001cc7c`
- `0x18001d4bc`
- `0x18001d8e4`
- `0x18001d954`
- `0x18001d9d8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001cd67`
- `OLEAUT32!__imp_SysAllocString` at `0x18001cd67`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cd5e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cd5e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001cd13`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001cd13`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001ccec`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001ccec`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18001cd02`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18001cd02`

## pseudocode

```c
HRESULT __fastcall ATL::CComSafeArray<unsigned short *,8>::Add(SAFEARRAY **a1, const OLECHAR **a2)
{
  HRESULT result; // eax
  LONG LowerBound; // edi
  int Count; // eax
  SAFEARRAY *v7; // rcx
  int v8; // eax
  int v9; // edi
  int v10; // esi
  __int64 v11; // rdi
  OLECHAR *v12; // rcx
  BSTR v13; // rdx
  SAFEARRAYBOUND psaboundNew; // [rsp+50h] [rbp+8h] BYREF

  if ( *a1 || (psaboundNew = 0, result = ATL::CComSafeArray<unsigned short *,8>::Create(a1, &psaboundNew), result >= 0) )
  {
    LowerBound = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(a1);
    Count = ATL::CComSafeArray<unsigned short *,8>::GetCount(a1);
    v7 = *a1;
    psaboundNew.cElements = Count + 1;
    psaboundNew.lLbound = LowerBound;
    if ( !v7 )
      ATL::AtlThrowImpl(-2147467259);
    if ( (v7->fFeatures & 0x10) != 0 )
    {
      return -2147467259;
    }
    else
    {
      result = SafeArrayUnlock(v7);
      if ( result >= 0 )
      {
        result = SafeArrayRedim(*a1, &psaboundNew);
        if ( result >= 0 )
        {
          result = SafeArrayLock(*a1);
          if ( result >= 0 )
          {
            v8 = ATL::CComSafeArray<unsigned short *,8>::GetCount(a1);
            if ( *a2
              && (v9 = v8 - 1 + LowerBound, v10 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(a1), v9 >= v10)
              && v9 <= (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(a1) )
            {
              v11 = v9 - v10;
              v12 = (OLECHAR *)*((_QWORD *)(*a1)->pvData + v11);
              if ( v12 )
                SysFreeString(v12);
              v13 = SysAllocString(*a2);
              if ( v13 )
              {
                result = 0;
                *((_QWORD *)(*a1)->pvData + v11) = v13;
              }
              else
              {
                return -2147024882;
              }
            }
            else
            {
              return -2147024809;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001cc7c  push    rbx
0x18001cc7e  push    rsi
0x18001cc7f  push    rdi
0x18001cc80  push    r14
0x18001cc82  sub     rsp, 28h
0x18001cc86  cmp     qword ptr [rcx], 0
0x18001cc8a  mov     r14, rdx
0x18001cc8d  mov     rbx, rcx
0x18001cc90  jnz     short loc_18001CCAD
0x18001cc92  lea     rdx, [rsp+48h+psaboundNew]
0x18001cc97  mov     qword ptr [rsp+48h+psaboundNew.cElements], 0
0x18001cca0  call    ?Create@?$CComSafeArray@PEAG$07@ATL@@QEAAJPEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<ushort *,8>::Create(tagSAFEARRAYBOUND const *,uint)
0x18001cca5  test    eax, eax
0x18001cca7  js      loc_18001CD90
0x18001ccad  mov     rcx, rbx
0x18001ccb0  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001ccb5  mov     rcx, rbx
0x18001ccb8  mov     edi, eax
0x18001ccba  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18001ccbf  mov     rcx, [rbx]; psa
0x18001ccc2  inc     eax
0x18001ccc4  mov     [rsp+48h+psaboundNew.cElements], eax
0x18001ccc8  mov     [rsp+48h+psaboundNew.lLbound], edi
0x18001cccc  test    rcx, rcx
0x18001cccf  jnz     short loc_18001CCDC
0x18001ccd1  mov     ecx, 80004005h; int
0x18001ccd6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001ccdc  test    byte ptr [rcx+2], 10h
0x18001cce0  jz      short loc_18001CCEC
0x18001cce2  mov     eax, 80004005h
0x18001cce7  jmp     loc_18001CD90
0x18001ccec  call    cs:__imp_SafeArrayUnlock
0x18001ccf2  test    eax, eax
0x18001ccf4  js      loc_18001CD90
0x18001ccfa  mov     rcx, [rbx]; psa
0x18001ccfd  lea     rdx, [rsp+48h+psaboundNew]; psaboundNew
0x18001cd02  call    cs:__imp_SafeArrayRedim
0x18001cd08  test    eax, eax
0x18001cd0a  js      loc_18001CD90
0x18001cd10  mov     rcx, [rbx]; psa
0x18001cd13  call    cs:__imp_SafeArrayLock
0x18001cd19  test    eax, eax
0x18001cd1b  js      short loc_18001CD90
0x18001cd1d  mov     rcx, rbx
0x18001cd20  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18001cd25  cmp     qword ptr [r14], 0
0x18001cd29  jz      short loc_18001CD8B
0x18001cd2b  dec     eax
0x18001cd2d  mov     rcx, rbx
0x18001cd30  add     edi, eax
0x18001cd32  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001cd37  mov     esi, eax
0x18001cd39  cmp     edi, eax
0x18001cd3b  jl      short loc_18001CD8B
0x18001cd3d  mov     rcx, rbx
0x18001cd40  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001cd45  cmp     edi, eax
0x18001cd47  jg      short loc_18001CD8B
0x18001cd49  mov     rax, [rbx]
0x18001cd4c  sub     edi, esi
0x18001cd4e  movsxd  rdi, edi
0x18001cd51  mov     rcx, [rax+10h]
0x18001cd55  mov     rcx, [rcx+rdi*8]; bstrString
0x18001cd59  test    rcx, rcx
0x18001cd5c  jz      short loc_18001CD64
0x18001cd5e  call    cs:__imp_SysFreeString
0x18001cd64  mov     rcx, [r14]; psz
0x18001cd67  call    cs:__imp_SysAllocString
0x18001cd6d  mov     rdx, rax
0x18001cd70  test    rax, rax
0x18001cd73  jnz     short loc_18001CD7C
0x18001cd75  mov     eax, 8007000Eh
0x18001cd7a  jmp     short loc_18001CD90
0x18001cd7c  mov     rax, [rbx]
0x18001cd7f  mov     rcx, [rax+10h]
0x18001cd83  xor     eax, eax
0x18001cd85  mov     [rcx+rdi*8], rdx
0x18001cd89  jmp     short loc_18001CD90
0x18001cd8b  mov     eax, 80070057h
0x18001cd90  add     rsp, 28h
0x18001cd94  pop     r14
0x18001cd96  pop     rdi
0x18001cd97  pop     rsi
0x18001cd98  pop     rbx
0x18001cd99  retn
```
