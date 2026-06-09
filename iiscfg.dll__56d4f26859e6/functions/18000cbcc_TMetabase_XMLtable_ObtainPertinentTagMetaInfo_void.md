# TMetabase_XMLtable::ObtainPertinentTagMetaInfo(void)

- ea: `0x18000cbcc`
- end: `0x18000cdf8`
- name: `?ObtainPertinentTagMetaInfo@TMetabase_XMLtable@@AEAAJXZ`
- size: `556`
- prototype: `__int64 __fastcall(TMetabase_XMLtable *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000c4d0`

## callees

- `0x18000cbcc`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000cccc`
- `ole32!CoTaskMemAlloc` at `0x18000cccc`

## string_xrefs

- `0x18000cd61`: `IIsConfigObject`

## pseudocode

```c
__int64 __fastcall TMetabase_XMLtable::ObtainPertinentTagMetaInfo(TMetabase_XMLtable *this)
{
  __int64 v2; // rcx
  _QWORD *v3; // r15
  __int64 result; // rax
  __int64 v5; // rcx
  LPVOID v6; // rax
  __int64 v7; // rdi
  unsigned int v8; // esi
  unsigned int *v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // ecx
  __int64 v13; // [rsp+28h] [rbp-71h]
  unsigned int v14[4]; // [rsp+50h] [rbp-49h] BYREF
  const wchar_t *v15; // [rsp+60h] [rbp-39h] BYREF
  int v16; // [rsp+68h] [rbp-31h]
  int v17; // [rsp+6Ch] [rbp-2Dh]
  __int64 v18; // [rsp+70h] [rbp-29h]
  __int64 v19; // [rsp+78h] [rbp-21h] BYREF
  int v20; // [rsp+80h] [rbp-19h]
  int v21; // [rsp+84h] [rbp-15h]
  __int64 v22; // [rsp+88h] [rbp-11h]
  const wchar_t *v23; // [rsp+90h] [rbp-9h]
  __int64 v24; // [rsp+98h] [rbp-1h]
  __int64 v25; // [rsp+A0h] [rbp+7h]

  v19 = *((_QWORD *)this + 222);
  v20 = 2;
  v2 = *((_QWORD *)this + 214);
  v23 = L"MBProperty";
  v21 = -268435455;
  v22 = 130;
  v3 = (_QWORD *)((char *)this + 1744);
  v24 = 2;
  v25 = 130;
  result = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, unsigned int *, int, _DWORD, char *))(*(_QWORD *)v2 + 24LL))(
             v2,
             L"META",
             L"TAGMETA",
             &v19,
             &TMetabase_XMLtable::m_kTwo,
             3,
             0,
             (char *)this + 1744);
  if ( (int)result >= 0 )
  {
    v5 = *v3;
    v14[0] = 0;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v5 + 40LL))(
               v5,
               0,
               0,
               v14,
               0);
    if ( (int)result >= 0 )
    {
      v6 = CoTaskMemAlloc(saturated_mul(v14[0], 0x30u));
      *((_QWORD *)this + 199) = v6;
      if ( v6 )
      {
        v7 = 0;
        v8 = -1;
        while ( (unsigned int)v7 < v14[0] )
        {
          v13 = 48 * v7 + *((_QWORD *)this + 199);
          result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*v3 + 32LL))(
                     *v3,
                     (unsigned int)v7,
                     6);
          if ( (int)result < 0 )
            return result;
          v9 = *(unsigned int **)(*((_QWORD *)this + 199) + 48 * v7 + 8);
          if ( v8 != *v9 )
          {
            v8 = *v9;
            *((_DWORD *)this + 2 * *v9 + 329) = v7;
          }
          ++*((_DWORD *)this + 2 * v8 + 330);
          v7 = (unsigned int)(v7 + 1);
        }
        v10 = *((_QWORD *)this + 214);
        v23 = L"IIsConfigObject";
        v15 = L"ByTableAndTagNameOnly";
        v16 = 2;
        v17 = -268435452;
        v18 = 130;
        LODWORD(v13) = 3;
        v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t **, unsigned int *, __int64, _DWORD, char *))(*(_QWORD *)v10 + 24LL))(
                v10,
                L"META",
                L"TAGMETA",
                &v15,
                &TMetabase_XMLtable::m_kThree,
                v13,
                0,
                (char *)this + 1752);
        v12 = 0;
        if ( v11 < 0 )
          return (unsigned int)v11;
        return v12;
      }
      else
      {
        return 2147942414LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000cbcc  push    rbp
0x18000cbce  push    rbx
0x18000cbcf  push    rsi
0x18000cbd0  push    rdi
0x18000cbd1  push    r14
0x18000cbd3  push    r15
0x18000cbd5  lea     rbp, [rsp-2Fh]
0x18000cbda  sub     rsp, 0C8h
0x18000cbe1  mov     rax, cs:__security_cookie
0x18000cbe8  xor     rax, rsp
0x18000cbeb  mov     [rbp+57h+var_40], rax
0x18000cbef  mov     rax, [rcx+6F0h]
0x18000cbf6  lea     rdx, ?m_kTwo@TMetabase_XMLtable@@0KA; ulong TMetabase_XMLtable::m_kTwo
0x18000cbfd  mov     [rbp+57h+var_78], rax
0x18000cc01  lea     r9, [rbp+57h+var_78]
0x18000cc05  mov     rbx, rcx
0x18000cc08  mov     [rbp+57h+var_70], 2
0x18000cc0f  mov     rcx, [rcx+6B0h]
0x18000cc16  lea     rax, aMbproperty; "MBProperty"
0x18000cc1d  mov     [rbp+57h+var_60], rax
0x18000cc21  lea     r8, aTagmeta; "TAGMETA"
0x18000cc28  mov     [rbp+57h+var_6C], 0F0000001h
0x18000cc2f  mov     [rbp+57h+var_68], 82h
0x18000cc37  lea     r15, [rbx+6D0h]
0x18000cc3e  mov     [rsp+0F0h+var_B8], r15
0x18000cc43  mov     [rbp+57h+var_58], 2
0x18000cc4b  mov     [rbp+57h+var_50], 82h
0x18000cc53  mov     rax, [rcx]
0x18000cc56  mov     [rsp+0F0h+var_C0], 0
0x18000cc5e  mov     dword ptr [rsp+0F0h+var_C8], 3
0x18000cc66  mov     [rsp+0F0h+var_D0], rdx
0x18000cc6b  lea     rdx, aMeta; "META"
0x18000cc72  mov     rax, [rax+18h]
0x18000cc76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc7b  test    eax, eax
0x18000cc7d  js      loc_18000CDDC
0x18000cc83  mov     rcx, [r15]
0x18000cc86  lea     r9, [rbp+57h+var_A0]
0x18000cc8a  mov     [rbp+57h+var_A0], 0
0x18000cc91  xor     r8d, r8d
0x18000cc94  xor     edx, edx
0x18000cc96  mov     [rsp+0F0h+var_D0], 0
0x18000cc9f  mov     rax, [rcx]
0x18000cca2  mov     rax, [rax+28h]
0x18000cca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccab  test    eax, eax
0x18000ccad  js      loc_18000CDDC
0x18000ccb3  mov     ecx, [rbp+57h+var_A0]
0x18000ccb6  mov     eax, 30h ; '0'
0x18000ccbb  mul     rcx
0x18000ccbe  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ccc5  cmovb   rax, rcx
0x18000ccc9  mov     rcx, rax; cb
0x18000cccc  call    cs:__imp_CoTaskMemAlloc
0x18000ccd2  mov     [rbx+638h], rax
0x18000ccd9  test    rax, rax
0x18000ccdc  jnz     short loc_18000CCE8
0x18000ccde  mov     eax, 8007000Eh
0x18000cce3  jmp     loc_18000CDDC
0x18000cce8  xor     edi, edi
0x18000ccea  or      esi, 0FFFFFFFFh
0x18000cced  cmp     edi, [rbp+57h+var_A0]
0x18000ccf0  jnb     short loc_18000CD5A
0x18000ccf2  mov     rcx, [r15]
0x18000ccf5  lea     r14, [rdi+rdi*2]
0x18000ccf9  mov     r8, [rbx+638h]
0x18000cd00  xor     r9d, r9d
0x18000cd03  shl     r14, 4
0x18000cd07  add     r8, r14
0x18000cd0a  mov     rdx, [rcx]
0x18000cd0d  mov     [rsp+0F0h+var_C8], r8
0x18000cd12  lea     r8d, [r9+6]
0x18000cd16  mov     [rsp+0F0h+var_D0], 0
0x18000cd1f  mov     rax, [rdx+20h]
0x18000cd23  mov     edx, edi
0x18000cd25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd2a  test    eax, eax
0x18000cd2c  js      loc_18000CDDC
0x18000cd32  mov     rax, [rbx+638h]
0x18000cd39  mov     rcx, [rax+r14+8]
0x18000cd3e  cmp     esi, [rcx]
0x18000cd40  jz      short loc_18000CD4D
0x18000cd42  mov     esi, [rcx]
0x18000cd44  mov     eax, esi
0x18000cd46  mov     [rbx+rax*8+524h], edi
0x18000cd4d  mov     eax, esi
0x18000cd4f  inc     dword ptr [rbx+rax*8+528h]
0x18000cd56  inc     edi
0x18000cd58  jmp     short loc_18000CCED
0x18000cd5a  mov     rcx, [rbx+6B0h]
0x18000cd61  lea     rax, aIisconfigobjec; "IIsConfigObject"
0x18000cd68  mov     [rbp+57h+var_60], rax
0x18000cd6c  lea     r9, [rbx+6D8h]
0x18000cd73  mov     [rsp+0F0h+var_B8], r9
0x18000cd78  lea     rax, aBytableandtagn; "ByTableAndTagNameOnly"
0x18000cd7f  mov     [rbp+57h+var_90], rax
0x18000cd83  lea     r9, ?m_kThree@TMetabase_XMLtable@@0KA; ulong TMetabase_XMLtable::m_kThree
0x18000cd8a  mov     [rbp+57h+var_88], 2
0x18000cd91  lea     r8, aTagmeta; "TAGMETA"
0x18000cd98  mov     [rbp+57h+var_84], 0F0000004h
0x18000cd9f  lea     rdx, aMeta; "META"
0x18000cda6  mov     [rbp+57h+var_80], 82h
0x18000cdae  mov     rax, [rcx]
0x18000cdb1  mov     [rsp+0F0h+var_C0], 0
0x18000cdb9  mov     dword ptr [rsp+0F0h+var_C8], 3
0x18000cdc1  mov     [rsp+0F0h+var_D0], r9
0x18000cdc6  lea     r9, [rbp+57h+var_90]
0x18000cdca  mov     rax, [rax+18h]
0x18000cdce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdd3  xor     ecx, ecx
0x18000cdd5  test    eax, eax
0x18000cdd7  cmovs   ecx, eax
0x18000cdda  mov     eax, ecx
0x18000cddc  mov     rcx, [rbp+57h+var_40]
0x18000cde0  xor     rcx, rsp; StackCookie
0x18000cde3  call    __security_check_cookie
0x18000cde8  add     rsp, 0C8h
0x18000cdef  pop     r15
0x18000cdf1  pop     r14
0x18000cdf3  pop     rdi
0x18000cdf4  pop     rsi
0x18000cdf5  pop     rbx
0x18000cdf6  pop     rbp
0x18000cdf7  retn
```
