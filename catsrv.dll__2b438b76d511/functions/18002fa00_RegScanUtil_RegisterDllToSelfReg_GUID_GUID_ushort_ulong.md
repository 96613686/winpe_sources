# RegScanUtil::RegisterDllToSelfReg(_GUID,_GUID,ushort *,ulong)

- ea: `0x18002fa00`
- end: `0x18002fbaf`
- name: `?RegisterDllToSelfReg@RegScanUtil@@SAJU_GUID@@0PEAGK@Z`
- size: `431`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fe08`

## callees

- `0x18002fa00`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb8f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fa64`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fa64`

## pseudocode

```c
__int64 __fastcall RegScanUtil::RegisterDllToSelfReg(struct _GUID *a1, struct _GUID *a2, unsigned __int16 *a3)
{
  HRESULT v5; // esi
  __int128 v6; // xmm1
  __int64 (__fastcall *v7)(LPVOID, __int128 *, __int128 *, unsigned __int16 **, int, int, _QWORD, _DWORD, LPVOID *, unsigned int *, LPVOID *, LPVOID *, LPVOID *, LPVOID *); // rax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  LPVOID *i; // rcx
  LPVOID v12; // [rsp+88h] [rbp-9h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp-1h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+7h] BYREF
  LPVOID v15; // [rsp+A0h] [rbp+Fh] BYREF
  LPVOID v16; // [rsp+A8h] [rbp+17h] BYREF
  LPVOID v17; // [rsp+B0h] [rbp+1Fh] BYREF
  __int128 v18; // [rsp+B8h] [rbp+27h] BYREF
  __int128 v19; // [rsp+C8h] [rbp+37h] BYREF
  unsigned __int16 *v20; // [rsp+108h] [rbp+77h] BYREF
  unsigned int v21; // [rsp+110h] [rbp+7Fh] BYREF

  v20 = a3;
  ppv = 0;
  pv = 0;
  v21 = 0;
  v15 = 0;
  v12 = 0;
  v16 = 0;
  v17 = 0;
  v5 = CoCreateInstance(
         &GUID_8db2180f_bd29_11d1_8b7e_00c04fd7a924,
         0,
         3u,
         &GUID_971668dc_c3fe_4ea1_9643_0c7230f494a1,
         &ppv);
  if ( v5 >= 0 )
  {
    v6 = (__int128)*a2;
    v7 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, unsigned __int16 **, int, int, _QWORD, _DWORD, LPVOID *, unsigned int *, LPVOID *, LPVOID *, LPVOID *, LPVOID *))(*(_QWORD *)ppv + 64LL);
    v18 = (__int128)*a1;
    v19 = v6;
    v5 = v7(ppv, &v19, &v18, &v20, 1, 12288, 0, 0, &pv, &v21, &v15, &v12, &v16, &v17);
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v15 )
  {
    CoTaskMemFree(v15);
    v15 = 0;
  }
  v8 = v21;
  v9 = 0;
  for ( i = (LPVOID *)v12; v9 < v8; ++v9 )
  {
    if ( i[v9] )
    {
      CoTaskMemFree(i[v9]);
      *((_QWORD *)v12 + v9) = 0;
      v8 = v21;
      i = (LPVOID *)v12;
    }
  }
  if ( i )
  {
    CoTaskMemFree(i);
    v12 = 0;
  }
  if ( v16 )
  {
    CoTaskMemFree(v16);
    v16 = 0;
  }
  if ( v17 )
    CoTaskMemFree(v17);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002fa00  mov     rax, rsp
0x18002fa03  mov     [rax+8], rbx
0x18002fa07  mov     [rax+10h], rsi
0x18002fa0b  mov     [rax+20h], r9d
0x18002fa0f  mov     [rax+18h], r8
0x18002fa13  push    rbp
0x18002fa14  push    rdi
0x18002fa15  push    r14
0x18002fa17  lea     rbp, [rax-5Fh]
0x18002fa1b  sub     rsp, 0D0h
0x18002fa22  xor     r14d, r14d
0x18002fa25  lea     rax, [rbp+57h+var_58]
0x18002fa29  mov     rbx, rdx
0x18002fa2c  mov     [rbp+57h+var_58], r14
0x18002fa30  mov     rdi, rcx
0x18002fa33  mov     [rbp+57h+pv], r14
0x18002fa37  lea     r9, _GUID_971668dc_c3fe_4ea1_9643_0c7230f494a1; riid
0x18002fa3e  mov     [rbp+57h+arg_18], r14d
0x18002fa42  lea     r8d, [r14+3]; dwClsContext
0x18002fa46  mov     [rbp+57h+var_48], r14
0x18002fa4a  xor     edx, edx; pUnkOuter
0x18002fa4c  mov     [rbp+57h+var_60], r14
0x18002fa50  lea     rcx, _GUID_8db2180f_bd29_11d1_8b7e_00c04fd7a924; rclsid
0x18002fa57  mov     [rbp+57h+var_40], r14
0x18002fa5b  mov     [rbp+57h+var_38], r14
0x18002fa5f  mov     [rsp+0E0h+ppv], rax; ppv
0x18002fa64  call    cs:__imp_CoCreateInstance
0x18002fa6a  mov     esi, eax
0x18002fa6c  test    eax, eax
0x18002fa6e  js      short loc_18002FAEE
0x18002fa70  mov     rcx, [rbp+57h+var_58]
0x18002fa74  lea     rdx, [rbp+57h+var_38]
0x18002fa78  movaps  xmm0, xmmword ptr [rdi]
0x18002fa7b  lea     r9, [rbp+57h+arg_10]
0x18002fa7f  movaps  xmm1, xmmword ptr [rbx]
0x18002fa82  lea     r8, [rbp+57h+var_30]
0x18002fa86  mov     [rsp+0E0h+var_78], rdx
0x18002fa8b  lea     rdx, [rbp+57h+var_40]
0x18002fa8f  mov     rax, [rcx]
0x18002fa92  mov     [rsp+0E0h+var_80], rdx
0x18002fa97  lea     rdx, [rbp+57h+var_60]
0x18002fa9b  mov     [rsp+0E0h+var_88], rdx
0x18002faa0  lea     rdx, [rbp+57h+var_48]
0x18002faa4  mov     [rsp+0E0h+var_90], rdx
0x18002faa9  lea     rdx, [rbp+57h+arg_18]
0x18002faad  mov     rax, [rax+40h]
0x18002fab1  mov     [rsp+0E0h+var_98], rdx
0x18002fab6  lea     rdx, [rbp+57h+pv]
0x18002faba  mov     [rsp+0E0h+var_A0], rdx
0x18002fabf  lea     rdx, [rbp+57h+var_20]
0x18002fac3  mov     dword ptr [rsp+0E0h+var_A8], r14d
0x18002fac8  mov     qword ptr [rsp+0E0h+var_B0], r14
0x18002facd  mov     dword ptr [rsp+0E0h+var_B8], 3000h
0x18002fad5  mov     dword ptr [rsp+0E0h+ppv], 1
0x18002fadd  movdqa  [rbp+57h+var_30], xmm0
0x18002fae2  movdqa  [rbp+57h+var_20], xmm1
0x18002fae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002faec  mov     esi, eax
0x18002faee  mov     rcx, [rbp+57h+var_58]
0x18002faf2  test    rcx, rcx
0x18002faf5  jz      short loc_18002FB07
0x18002faf7  mov     rax, [rcx]
0x18002fafa  mov     rax, [rax+10h]
0x18002fafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb03  mov     [rbp+57h+var_58], r14
0x18002fb07  mov     rcx, [rbp+57h+pv]; pv
0x18002fb0b  test    rcx, rcx
0x18002fb0e  jz      short loc_18002FB1A
0x18002fb10  call    cs:__imp_CoTaskMemFree
0x18002fb16  mov     [rbp+57h+pv], r14
0x18002fb1a  mov     rcx, [rbp+57h+var_48]; pv
0x18002fb1e  test    rcx, rcx
0x18002fb21  jz      short loc_18002FB2D
0x18002fb23  call    cs:__imp_CoTaskMemFree
0x18002fb29  mov     [rbp+57h+var_48], r14
0x18002fb2d  mov     eax, [rbp+57h+arg_18]
0x18002fb30  mov     ebx, r14d
0x18002fb33  mov     rcx, [rbp+57h+var_60]
0x18002fb37  test    eax, eax
0x18002fb39  jz      short loc_18002FB64
0x18002fb3b  mov     edi, ebx
0x18002fb3d  mov     rdx, [rcx+rdi*8]
0x18002fb41  test    rdx, rdx
0x18002fb44  jz      short loc_18002FB5E
0x18002fb46  mov     rcx, rdx; pv
0x18002fb49  call    cs:__imp_CoTaskMemFree
0x18002fb4f  mov     rax, [rbp+57h+var_60]
0x18002fb53  mov     [rax+rdi*8], r14
0x18002fb57  mov     eax, [rbp+57h+arg_18]
0x18002fb5a  mov     rcx, [rbp+57h+var_60]; pv
0x18002fb5e  inc     ebx
0x18002fb60  cmp     ebx, eax
0x18002fb62  jb      short loc_18002FB3B
0x18002fb64  test    rcx, rcx
0x18002fb67  jz      short loc_18002FB73
0x18002fb69  call    cs:__imp_CoTaskMemFree
0x18002fb6f  mov     [rbp+57h+var_60], r14
0x18002fb73  mov     rcx, [rbp+57h+var_40]; pv
0x18002fb77  test    rcx, rcx
0x18002fb7a  jz      short loc_18002FB86
0x18002fb7c  call    cs:__imp_CoTaskMemFree
0x18002fb82  mov     [rbp+57h+var_40], r14
0x18002fb86  mov     rcx, [rbp+57h+var_38]; pv
0x18002fb8a  test    rcx, rcx
0x18002fb8d  jz      short loc_18002FB95
0x18002fb8f  call    cs:__imp_CoTaskMemFree
0x18002fb95  lea     r11, [rsp+0E0h+var_10]
0x18002fb9d  mov     eax, esi
0x18002fb9f  mov     rbx, [r11+20h]
0x18002fba3  mov     rsi, [r11+28h]
0x18002fba7  mov     rsp, r11
0x18002fbaa  pop     r14
0x18002fbac  pop     rdi
0x18002fbad  pop     rbp
0x18002fbae  retn
```
