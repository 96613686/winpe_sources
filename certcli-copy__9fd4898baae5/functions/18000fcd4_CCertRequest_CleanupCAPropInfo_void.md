# CCertRequest::_CleanupCAPropInfo(void)

- ea: `0x18000fcd4`
- end: `0x18000fdd5`
- name: `?_CleanupCAPropInfo@CCertRequest@@AEAAXXZ`
- size: `257`
- prototype: `void __fastcall(CCertRequest *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fddc`

## callees

- `0x18000fcd4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fdb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fdb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd97`

## pseudocode

```c
void __fastcall CCertRequest::_CleanupCAPropInfo(CCertRequest *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx

  v2 = (void *)*((_QWORD *)this + 41);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 41) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 43);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 43) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 45);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 45) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 29);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 29) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 31);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)this + 31) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 33);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)this + 33) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 37);
  if ( v8 )
  {
    CoTaskMemFree(v8);
    *((_QWORD *)this + 37) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 35);
  if ( v9 )
  {
    LocalFree(v9);
    *((_QWORD *)this + 35) = 0;
  }
  *((_DWORD *)this + 72) = 0;
}

```

## disassembly

```asm
0x18000fcd4  push    rbx
0x18000fcd6  sub     rsp, 20h
0x18000fcda  mov     rbx, rcx
0x18000fcdd  mov     rcx, [rcx+148h]; pv
0x18000fce4  test    rcx, rcx
0x18000fce7  jz      short loc_18000FCFA
0x18000fce9  call    cs:__imp_CoTaskMemFree
0x18000fcef  mov     qword ptr [rbx+148h], 0
0x18000fcfa  mov     rcx, [rbx+158h]; pv
0x18000fd01  test    rcx, rcx
0x18000fd04  jz      short loc_18000FD17
0x18000fd06  call    cs:__imp_CoTaskMemFree
0x18000fd0c  mov     qword ptr [rbx+158h], 0
0x18000fd17  mov     rcx, [rbx+168h]; pv
0x18000fd1e  test    rcx, rcx
0x18000fd21  jz      short loc_18000FD34
0x18000fd23  call    cs:__imp_CoTaskMemFree
0x18000fd29  mov     qword ptr [rbx+168h], 0
0x18000fd34  mov     rcx, [rbx+0E8h]; pv
0x18000fd3b  test    rcx, rcx
0x18000fd3e  jz      short loc_18000FD51
0x18000fd40  call    cs:__imp_CoTaskMemFree
0x18000fd46  mov     qword ptr [rbx+0E8h], 0
0x18000fd51  mov     rcx, [rbx+0F8h]; pv
0x18000fd58  test    rcx, rcx
0x18000fd5b  jz      short loc_18000FD6E
0x18000fd5d  call    cs:__imp_CoTaskMemFree
0x18000fd63  mov     qword ptr [rbx+0F8h], 0
0x18000fd6e  mov     rcx, [rbx+108h]; pv
0x18000fd75  test    rcx, rcx
0x18000fd78  jz      short loc_18000FD8B
0x18000fd7a  call    cs:__imp_CoTaskMemFree
0x18000fd80  mov     qword ptr [rbx+108h], 0
0x18000fd8b  mov     rcx, [rbx+128h]; pv
0x18000fd92  test    rcx, rcx
0x18000fd95  jz      short loc_18000FDA8
0x18000fd97  call    cs:__imp_CoTaskMemFree
0x18000fd9d  mov     qword ptr [rbx+128h], 0
0x18000fda8  mov     rcx, [rbx+118h]; hMem
0x18000fdaf  test    rcx, rcx
0x18000fdb2  jz      short loc_18000FDC5
0x18000fdb4  call    cs:__imp_LocalFree
0x18000fdba  mov     qword ptr [rbx+118h], 0
0x18000fdc5  mov     dword ptr [rbx+120h], 0
0x18000fdcf  add     rsp, 20h
0x18000fdd3  pop     rbx
0x18000fdd4  retn
```
