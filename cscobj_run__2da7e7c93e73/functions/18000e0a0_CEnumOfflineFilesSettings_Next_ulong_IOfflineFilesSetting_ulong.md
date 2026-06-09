# CEnumOfflineFilesSettings::Next(ulong,IOfflineFilesSetting * *,ulong *)

- ea: `0x18000e0a0`
- end: `0x18000e204`
- name: `?Next@CEnumOfflineFilesSettings@@UEAAJKPEAPEAUIOfflineFilesSetting@@PEAK@Z`
- size: `356`
- prototype: `__int64 __fastcall(CEnumOfflineFilesSettings *__hidden this, unsigned int, struct IOfflineFilesSetting **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006c00`
- `0x180008d78`
- `0x18000e0a0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e19e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e19e`

## pseudocode

```c
__int64 __fastcall CEnumOfflineFilesSettings::Next(
        CEnumOfflineFilesSettings *this,
        unsigned int a2,
        struct IOfflineFilesSetting **a3,
        unsigned int *a4)
{
  unsigned int v4; // r15d
  __int64 *v9; // rbx
  unsigned int v10; // esi
  int v11; // edi
  __int64 v12; // rcx
  struct IOfflineFilesSetting *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rbx
  LPVOID pv[3]; // [rsp+20h] [rbp-18h] BYREF
  void *v17; // [rsp+90h] [rbp+58h] BYREF

  v4 = 0;
  if ( !a3 )
    return 2147500035LL;
  if ( !a4 && a2 != 1 )
    return 2147942487LL;
  v9 = (__int64 *)((char *)this + 16);
  v10 = 0;
  if ( *((_QWORD *)this + 2)
    || (v17 = 0,
        v11 = CInterfaceInGITBase::_Unmarshal(
                (CEnumOfflineFilesSettings *)((char *)this + 24),
                &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
                &v17),
        v11 >= 0)
    && (v11 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)v17 + 240LL))(v17, v9),
        (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17),
        v11 >= 0) )
  {
    v11 = 0;
    while ( v10 < a2 )
    {
      v12 = *v9;
      pv[0] = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v12 + 24LL))(v12, pv);
      if ( !v11 )
      {
        v17 = 0;
        v11 = COfflineFilesSettingProxy::CreateInstance(
                (const unsigned __int16 *)pv[0],
                &GUID_d871d3f7_f613_48a1_827e_7a34e560fff6,
                &v17);
        if ( v11 >= 0 )
        {
          v13 = (struct IOfflineFilesSetting *)v17;
          v14 = v10++;
          v17 = 0;
          a3[v14] = v13;
        }
        CoTaskMemFree(pv[0]);
        if ( !v11 )
          continue;
      }
      if ( v11 < 0 )
      {
        if ( v10 )
        {
          do
          {
            v15 = v4;
            ((void (__fastcall *)(struct IOfflineFilesSetting *))a3[v4]->lpVtbl->Release)(a3[v4]);
            ++v4;
            a3[v15] = 0;
          }
          while ( v4 < v10 );
        }
        v10 = 0;
      }
      break;
    }
  }
  if ( a4 )
    *a4 = v10;
  if ( v11 >= 0 )
    return v10 != a2;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000e0a0  push    rbp
0x18000e0a2  push    rbx
0x18000e0a3  push    rsi
0x18000e0a4  push    rdi
0x18000e0a5  push    r12
0x18000e0a7  push    r13
0x18000e0a9  push    r14
0x18000e0ab  push    r15
0x18000e0ad  mov     rbp, rsp
0x18000e0b0  sub     rsp, 38h
0x18000e0b4  xor     r15d, r15d
0x18000e0b7  mov     r14, r9
0x18000e0ba  mov     r13, r8
0x18000e0bd  mov     r12d, edx
0x18000e0c0  test    r8, r8
0x18000e0c3  jnz     short loc_18000E0CF
0x18000e0c5  mov     eax, 80004003h
0x18000e0ca  jmp     loc_18000E1F3
0x18000e0cf  test    r14, r14
0x18000e0d2  jnz     short loc_18000E0E4
0x18000e0d4  cmp     r12d, 1
0x18000e0d8  jz      short loc_18000E0E4
0x18000e0da  mov     eax, 80070057h
0x18000e0df  jmp     loc_18000E1F3
0x18000e0e4  lea     rbx, [rcx+10h]
0x18000e0e8  mov     esi, r15d
0x18000e0eb  cmp     [rbx], r15
0x18000e0ee  jnz     short loc_18000E142
0x18000e0f0  add     rcx, 18h; this
0x18000e0f4  mov     [rbp+arg_10], r15
0x18000e0f8  lea     r8, [rbp+arg_10]; void **
0x18000e0fc  lea     rdx, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce; struct _GUID *
0x18000e103  call    ?_Unmarshal@CInterfaceInGITBase@@IEAAJAEBU_GUID@@PEAPEAX@Z; CInterfaceInGITBase::_Unmarshal(_GUID const &,void * *)
0x18000e108  mov     edi, eax
0x18000e10a  test    eax, eax
0x18000e10c  js      loc_18000E1DB
0x18000e112  mov     rcx, [rbp+arg_10]
0x18000e116  mov     rdx, rbx
0x18000e119  mov     rax, [rcx]
0x18000e11c  mov     rax, [rax+0F0h]
0x18000e123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e128  mov     rcx, [rbp+arg_10]
0x18000e12c  mov     edi, eax
0x18000e12e  mov     rax, [rcx]
0x18000e131  mov     rax, [rax+10h]
0x18000e135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e13a  test    edi, edi
0x18000e13c  js      loc_18000E1DB
0x18000e142  mov     edi, r15d
0x18000e145  cmp     esi, r12d
0x18000e148  jnb     loc_18000E1DB
0x18000e14e  mov     rcx, [rbx]
0x18000e151  lea     rdx, [rbp+pv]
0x18000e155  mov     [rbp+pv], r15
0x18000e159  mov     rax, [rcx]
0x18000e15c  mov     rax, [rax+18h]
0x18000e160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e165  mov     edi, eax
0x18000e167  test    eax, eax
0x18000e169  jnz     short loc_18000E1A8
0x18000e16b  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18000e16f  lea     r8, [rbp+arg_10]; void **
0x18000e173  lea     rdx, _GUID_d871d3f7_f613_48a1_827e_7a34e560fff6; struct _GUID *
0x18000e17a  mov     [rbp+arg_10], r15
0x18000e17e  call    ?CreateInstance@COfflineFilesSettingProxy@@SAJPEBGAEBU_GUID@@PEAPEAX@Z; COfflineFilesSettingProxy::CreateInstance(ushort const *,_GUID const &,void * *)
0x18000e183  mov     edi, eax
0x18000e185  test    eax, eax
0x18000e187  js      short loc_18000E19A
0x18000e189  mov     rax, [rbp+arg_10]
0x18000e18d  mov     ecx, esi
0x18000e18f  inc     esi
0x18000e191  mov     [rbp+arg_10], r15
0x18000e195  mov     [r13+rcx*8+0], rax
0x18000e19a  mov     rcx, [rbp+pv]; pv
0x18000e19e  call    cs:__imp_CoTaskMemFree
0x18000e1a4  test    edi, edi
0x18000e1a6  jz      short loc_18000E145
0x18000e1a8  test    edi, edi
0x18000e1aa  jns     short loc_18000E1DB
0x18000e1ac  test    esi, esi
0x18000e1ae  jz      short loc_18000E1D5
0x18000e1b0  mov     ebx, r15d
0x18000e1b3  mov     rcx, [r13+rbx*8+0]
0x18000e1b8  mov     rax, [rcx]
0x18000e1bb  mov     rax, [rax+10h]
0x18000e1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1c4  inc     r15d
0x18000e1c7  mov     qword ptr [r13+rbx*8+0], 0
0x18000e1d0  cmp     r15d, esi
0x18000e1d3  jb      short loc_18000E1B0
0x18000e1d5  xor     r15d, r15d
0x18000e1d8  mov     esi, r15d
0x18000e1db  test    r14, r14
0x18000e1de  jz      short loc_18000E1E3
0x18000e1e0  mov     [r14], esi
0x18000e1e3  test    edi, edi
0x18000e1e5  js      short loc_18000E1F1
0x18000e1e7  cmp     esi, r12d
0x18000e1ea  mov     edi, r15d
0x18000e1ed  setnz   dil
0x18000e1f1  mov     eax, edi
0x18000e1f3  add     rsp, 38h
0x18000e1f7  pop     r15
0x18000e1f9  pop     r14
0x18000e1fb  pop     r13
0x18000e1fd  pop     r12
0x18000e1ff  pop     rdi
0x18000e200  pop     rsi
0x18000e201  pop     rbx
0x18000e202  pop     rbp
0x18000e203  retn
```
