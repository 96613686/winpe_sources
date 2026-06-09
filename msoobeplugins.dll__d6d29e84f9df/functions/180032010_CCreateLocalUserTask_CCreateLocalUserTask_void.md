# CCreateLocalUserTask::~CCreateLocalUserTask(void)

- ea: `0x180032010`
- end: `0x1800320d8`
- name: `??1CCreateLocalUserTask@@EEAA@XZ`
- size: `200`
- prototype: `void __fastcall(CCreateLocalUserTask *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032160`

## callees

- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032068`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003209f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800320ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032068`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003209f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800320ac`

## pseudocode

```c
void __fastcall CCreateLocalUserTask::~CCreateLocalUserTask(CCreateLocalUserTask *this)
{
  _BYTE *v2; // rax
  __int64 v3; // rcx
  __int64 i; // rcx
  _BYTE *v5; // rax
  __int64 v6; // rcx
  __int64 j; // rcx

  *(_QWORD *)this = &CCreateLocalUserTask::`vftable'{for `Microsoft::WRL::Details::Selector<COOBETask,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<COOBETask>,ILocalAccountTaskPrivate>>'};
  *((_QWORD *)this + 67) = &CCreateLocalUserTask::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ILocalAccountTaskPrivate>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<COOBETask>,ILocalAccountTaskPrivate>>'};
  v2 = (_BYTE *)*((_QWORD *)this + 134);
  if ( v2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)&v2[2 * v3] );
    for ( i = 2 * v3; i; --i )
      *v2++ = 0;
    CoTaskMemFree(*((LPVOID *)this + 134));
  }
  v5 = (_BYTE *)*((_QWORD *)this + 135);
  if ( v5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&v5[2 * v6] );
    for ( j = 2 * v6; j; --j )
      *v5++ = 0;
    CoTaskMemFree(*((LPVOID *)this + 135));
  }
  CoTaskMemFree(*((LPVOID *)this + 136));
  *((_DWORD *)this + 137) = -1073741823;
  *(_QWORD *)this = &COOBETask::`vftable';
  _InterlockedDecrement(&g_cRefCount);
}

```

## disassembly

```asm
0x180032010  mov     [rsp+arg_0], rbx
0x180032015  push    rdi
0x180032016  sub     rsp, 20h
0x18003201a  mov     rbx, rcx
0x18003201d  lea     rax, ??_7CCreateLocalUserTask@@6B?$Selector@VCOOBETask@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCOOBETask@@@Details@23@UILocalAccountTaskPrivate@@@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@@; const CCreateLocalUserTask::`vftable'{for `Microsoft::WRL::Details::Selector<COOBETask,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<COOBETask>,ILocalAccountTaskPrivate>>'}
0x180032024  mov     [rcx], rax
0x180032027  lea     rax, ??_7CCreateLocalUserTask@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UILocalAccountTaskPrivate@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCOOBETask@@@Details@23@UILocalAccountTaskPrivate@@@234@@Details@WRL@Microsoft@@@; const CCreateLocalUserTask::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ILocalAccountTaskPrivate>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<COOBETask>,ILocalAccountTaskPrivate>>'}
0x18003202e  mov     [rcx+218h], rax
0x180032035  mov     rax, [rcx+430h]
0x18003203c  xor     edi, edi
0x18003203e  test    rax, rax
0x180032041  jz      short loc_18003206E
0x180032043  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180032047  inc     rcx
0x18003204a  cmp     [rax+rcx*2], di
0x18003204e  jnz     short loc_180032047
0x180032050  add     rcx, rcx
0x180032053  jz      short loc_180032061
0x180032055  mov     [rax], dil
0x180032058  inc     rax
0x18003205b  sub     rcx, 1
0x18003205f  jnz     short loc_180032055
0x180032061  mov     rcx, [rbx+430h]; pv
0x180032068  call    cs:__imp_CoTaskMemFree
0x18003206e  mov     rax, [rbx+438h]
0x180032075  test    rax, rax
0x180032078  jz      short loc_1800320A5
0x18003207a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003207e  inc     rcx
0x180032081  cmp     [rax+rcx*2], di
0x180032085  jnz     short loc_18003207E
0x180032087  add     rcx, rcx
0x18003208a  jz      short loc_180032098
0x18003208c  mov     [rax], dil
0x18003208f  inc     rax
0x180032092  sub     rcx, 1
0x180032096  jnz     short loc_18003208C
0x180032098  mov     rcx, [rbx+438h]; pv
0x18003209f  call    cs:__imp_CoTaskMemFree
0x1800320a5  mov     rcx, [rbx+440h]; pv
0x1800320ac  call    cs:__imp_CoTaskMemFree
0x1800320b2  mov     dword ptr [rbx+224h], 0C0000001h
0x1800320bc  lea     rax, ??_7COOBETask@@6B@; const COOBETask::`vftable'
0x1800320c3  mov     [rbx], rax
0x1800320c6  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x1800320cd  mov     rbx, [rsp+28h+arg_0]
0x1800320d2  add     rsp, 20h
0x1800320d6  pop     rdi
0x1800320d7  retn
```
