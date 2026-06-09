# RegScan::~RegScan(void)

- ea: `0x18004fdbc`
- end: `0x18004fece`
- name: `??1RegScan@@QEAA@XZ`
- size: `274`
- prototype: `void __fastcall(RegScan *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000eaf8`
- `0x18004fdbc`
- `0x180055c50`

## callees

- `0x180008dd0`
- `0x18004fdbc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fe0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fe1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fe3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fe4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fe58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fe9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004feaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fe0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fe1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fe3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fe4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fe58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004fe9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004feaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fe7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fe93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fe7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fe93`

## pseudocode

```c
void __fastcall RegScan::~RegScan(RegScan *this)
{
  int i; // edi
  void *v3; // rsi
  int j; // edi
  HKEY v5; // rcx
  HKEY v6; // rcx

  if ( *((_DWORD *)this + 32) )
    RegScanUtil::RefCountFile(*(_QWORD *)(*((_QWORD *)this + 12) + 104LL), 3);
  for ( i = 0; i < *((_DWORD *)this + 2); ++i )
  {
    v3 = *(void **)(*(_QWORD *)this + 8LL * i);
    if ( v3 )
    {
      RegScan::~RegScan(*(RegScan **)(*(_QWORD *)this + 8LL * i));
      CoTaskMemFree(v3);
    }
  }
  CoTaskMemFree(*(LPVOID *)this);
  for ( j = 0; j < *((_DWORD *)this + 6); ++j )
    CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 2) + 16LL * j));
  CoTaskMemFree(*((LPVOID *)this + 2));
  CoTaskMemFree(*((LPVOID *)this + 4));
  v5 = (HKEY)*((_QWORD *)this + 5);
  if ( ((unsigned __int64)(v5 + 0x20000000) & 0xFFFFFFFF7FFFFFFFuLL) != 0 )
    RegCloseKey(v5);
  v6 = (HKEY)*((_QWORD *)this + 6);
  if ( v6 && *((_QWORD *)this + 5) != 0xFFFFFFFF80000000uLL )
    RegCloseKey(v6);
  CoTaskMemFree(*((LPVOID *)this + 10));
  if ( *((_DWORD *)this + 23) )
  {
    CoTaskMemFree(*((LPVOID *)this + 13));
    *((_QWORD *)this + 13) = 0;
  }
}

```

## disassembly

```asm
0x18004fdbc  mov     [rsp+arg_0], rbx
0x18004fdc1  mov     [rsp+arg_8], rsi
0x18004fdc6  push    rdi
0x18004fdc7  sub     rsp, 20h
0x18004fdcb  mov     rbx, rcx
0x18004fdce  mov     r8d, [rcx+80h]
0x18004fdd5  test    r8d, r8d
0x18004fdd8  jz      short loc_18004FDEC
0x18004fdda  mov     rcx, [rcx+60h]
0x18004fdde  mov     edx, 3
0x18004fde3  mov     rcx, [rcx+68h]
0x18004fde7  call    ?RefCountFile@RegScanUtil@@CAJPEAGW4REF_COUNT_TYPE@1@K@Z; RegScanUtil::RefCountFile(ushort *,RegScanUtil::REF_COUNT_TYPE,ulong)
0x18004fdec  xor     edi, edi
0x18004fdee  cmp     [rbx+8], edi
0x18004fdf1  jle     short loc_18004FE1C
0x18004fdf3  movsxd  rcx, edi
0x18004fdf6  mov     rax, [rbx]
0x18004fdf9  mov     rsi, [rax+rcx*8]
0x18004fdfd  test    rsi, rsi
0x18004fe00  jz      short loc_18004FE15
0x18004fe02  mov     rcx, rsi; this
0x18004fe05  call    ??1RegScan@@QEAA@XZ; RegScan::~RegScan(void)
0x18004fe0a  nop
0x18004fe0b  mov     rcx, rsi; pv
0x18004fe0e  call    cs:__imp_CoTaskMemFree
0x18004fe14  nop
0x18004fe15  inc     edi
0x18004fe17  cmp     edi, [rbx+8]
0x18004fe1a  jl      short loc_18004FDF3
0x18004fe1c  mov     rcx, [rbx]; pv
0x18004fe1f  call    cs:__imp_CoTaskMemFree
0x18004fe25  nop
0x18004fe26  xor     edi, edi
0x18004fe28  cmp     [rbx+18h], edi
0x18004fe2b  jle     short loc_18004FE49
0x18004fe2d  movsxd  rcx, edi
0x18004fe30  add     rcx, rcx
0x18004fe33  mov     rax, [rbx+10h]
0x18004fe37  mov     rcx, [rax+rcx*8]; pv
0x18004fe3b  call    cs:__imp_CoTaskMemFree
0x18004fe41  nop
0x18004fe42  inc     edi
0x18004fe44  cmp     edi, [rbx+18h]
0x18004fe47  jl      short loc_18004FE2D
0x18004fe49  mov     rcx, [rbx+10h]; pv
0x18004fe4d  call    cs:__imp_CoTaskMemFree
0x18004fe53  nop
0x18004fe54  mov     rcx, [rbx+20h]; pv
0x18004fe58  call    cs:__imp_CoTaskMemFree
0x18004fe5e  nop
0x18004fe5f  mov     rcx, [rbx+28h]; hKey
0x18004fe63  mov     eax, 80000000h
0x18004fe68  add     rax, rcx
0x18004fe6b  mov     rdx, 0FFFFFFFF7FFFFFFFh
0x18004fe75  test    rdx, rax
0x18004fe78  jz      short loc_18004FE80
0x18004fe7a  call    cs:__imp_RegCloseKey
0x18004fe80  mov     rcx, [rbx+30h]; hKey
0x18004fe84  test    rcx, rcx
0x18004fe87  jz      short loc_18004FE9A
0x18004fe89  cmp     qword ptr [rbx+28h], 0FFFFFFFF80000000h
0x18004fe91  jz      short loc_18004FE9A
0x18004fe93  call    cs:__imp_RegCloseKey
0x18004fe99  nop
0x18004fe9a  mov     rcx, [rbx+50h]; pv
0x18004fe9e  call    cs:__imp_CoTaskMemFree
0x18004fea4  nop
0x18004fea5  cmp     dword ptr [rbx+5Ch], 0
0x18004fea9  jz      short loc_18004FEBE
0x18004feab  mov     rcx, [rbx+68h]; pv
0x18004feaf  call    cs:__imp_CoTaskMemFree
0x18004feb5  nop
0x18004feb6  mov     qword ptr [rbx+68h], 0
0x18004febe  mov     rbx, [rsp+28h+arg_0]
0x18004fec3  mov     rsi, [rsp+28h+arg_8]
0x18004fec8  add     rsp, 20h
0x18004fecc  pop     rdi
0x18004fecd  retn
```
