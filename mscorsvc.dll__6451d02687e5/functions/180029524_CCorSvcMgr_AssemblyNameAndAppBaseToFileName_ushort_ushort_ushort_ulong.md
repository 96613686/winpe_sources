# CCorSvcMgr::AssemblyNameAndAppBaseToFileName(ushort *,ushort *,ushort *,ulong)

- ea: `0x180029524`
- end: `0x1800298d9`
- name: `?AssemblyNameAndAppBaseToFileName@CCorSvcMgr@@AEAAXPEAG00K@Z`
- size: `949`
- prototype: `void __fastcall(CCorSvcMgr *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180028bdc`

## callees

- `0x180029524`
- `0x180034fd4`
- `0x18003f280`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18002972c`
- `KERNEL32!WaitForSingleObject` at `0x18002972c`
- `KERNEL32!CloseHandle` at `0x18002976e`
- `KERNEL32!CloseHandle` at `0x18002976e`
- `KERNEL32!CreateEventW` at `0x180029681`
- `KERNEL32!CreateEventW` at `0x180029681`
- `OLEAUT32!__imp_SysStringLen` at `0x18002960a`
- `OLEAUT32!__imp_SysStringLen` at `0x18002960a`
- `fusion!InitializeFusion` at `0x180029562`
- `fusion!InitializeFusion` at `0x180029562`
- `fusion!CreateApplicationContext` at `0x1800295df`
- `fusion!CreateApplicationContext` at `0x1800295df`
- `fusion!CreateAssemblyNameObject` at `0x18002959a`
- `fusion!CreateAssemblyNameObject` at `0x18002959a`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall CCorSvcMgr::AssemblyNameAndAppBaseToFileName(
        CCorSvcMgr *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int v7; // eax
  HRESULT v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 *v12; // rdi
  __int64 v13; // rbx
  UINT v14; // eax
  int v15; // eax
  __int64 *v16; // rdi
  LPASSEMBLYNAME v17; // rbx
  int v18; // eax
  int v19; // ebx
  int v20; // ecx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // [rsp+70h] [rbp-59h] BYREF
  int v26; // [rsp+78h] [rbp-51h]
  __int64 *v27; // [rsp+80h] [rbp-49h] BYREF
  int v28; // [rsp+88h] [rbp-41h]
  LPASSEMBLYNAME ppAssemblyNameObj; // [rsp+90h] [rbp-39h] BYREF
  int v30; // [rsp+98h] [rbp-31h]
  __int64 v31; // [rsp+A0h] [rbp-29h] BYREF
  int v32; // [rsp+A8h] [rbp-21h]
  __int64 v33; // [rsp+B0h] [rbp-19h] BYREF
  int v34; // [rsp+B8h] [rbp-11h]
  int v35; // [rsp+C0h] [rbp-9h] BYREF
  void **v36; // [rsp+C8h] [rbp-1h] BYREF
  int v37; // [rsp+D0h] [rbp+7h]
  int v38; // [rsp+D4h] [rbp+Bh]
  HANDLE hHandle; // [rsp+D8h] [rbp+Fh]
  __int64 *v40; // [rsp+E0h] [rbp+17h]
  __int64 *v41; // [rsp+E8h] [rbp+1Fh]

  v35 = 260;
  v7 = InitializeFusion();
  if ( v7 < 0 )
    ThrowHR(v7);
  v30 = 0;
  ppAssemblyNameObj = 0;
  v8 = CreateAssemblyNameObject(&ppAssemblyNameObj, a2, 1u, 0);
  if ( v8 < 0 )
    ThrowHR(v8);
  v9 = v30;
  if ( ppAssemblyNameObj )
    v9 = 1;
  v30 = v9;
  v28 = 0;
  v27 = 0;
  v10 = CreateApplicationContext(0, &v27);
  if ( v10 < 0 )
    ThrowHR(v10);
  v11 = v28;
  v12 = v27;
  if ( v27 )
    v11 = 1;
  v28 = v11;
  v13 = *v27;
  v14 = SysStringLen(a3);
  v15 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, unsigned __int16 *, _QWORD, _DWORD))(v13 + 40))(
          v12,
          L"APPBASE",
          a3,
          v14,
          0);
  if ( v15 < 0 )
    ThrowHR(v15);
  v26 = 0;
  v25 = 0;
  v16 = v27;
  v17 = ppAssemblyNameObj;
  v36 = &CBindSink::`vftable';
  v37 = 1;
  v38 = -2147467259;
  v40 = &v25;
  hHandle = CreateEventW(0, 0, 0, 0);
  v32 = 0;
  v41 = &v31;
  v31 = 0;
  v18 = ((__int64 (__fastcall *)(LPASSEMBLYNAME, GUID *, __int64 *))v17->lpVtbl->QueryInterface)(
          v17,
          &IID_IAssemblyNameBinder,
          &v31);
  v19 = v18;
  v20 = v32;
  if ( v31 )
    v20 = 1;
  v32 = v20;
  if ( v18 >= 0 )
  {
    v19 = (*(__int64 (__fastcall **)(__int64, GUID *, void ***, __int64 *, _QWORD, _QWORD, _QWORD, _DWORD, __int64 *, _QWORD))(*(_QWORD *)v31 + 24LL))(
            v31,
            &IID_IAssembly,
            &v36,
            v16,
            0,
            0,
            0,
            0,
            &v25,
            0);
    if ( v19 == -2147483638 )
    {
      WaitForSingleObject(hHandle, 0xFFFFFFFF);
      v19 = v38;
    }
    if ( v19 >= 0 && v25 )
      v19 = 0;
  }
  if ( v32 )
  {
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v32 = 0;
  }
  v36 = &CBindSink::`vftable';
  if ( hHandle )
    CloseHandle(hHandle);
  if ( v19 < 0 )
    ThrowHR(v19);
  v21 = v26;
  if ( v25 )
    v21 = 1;
  v26 = v21;
  v34 = 0;
  v33 = 0;
  v22 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v25)(v25, &IID_IAssembly, &v33);
  if ( v22 < 0 )
    ThrowHR(v22);
  v23 = v34;
  if ( v33 )
    v23 = 1;
  v34 = v23;
  v24 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, int *))(*(_QWORD *)v33 + 56LL))(v33, a4, &v35);
  if ( v24 < 0 )
    ThrowHR(v24);
  if ( v34 )
  {
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v34 = 0;
  }
  if ( v26 )
  {
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v26 = 0;
  }
  if ( v28 )
  {
    if ( v27 )
      (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
    v28 = 0;
  }
  if ( v30 )
  {
    if ( ppAssemblyNameObj )
      ((void (__fastcall *)(LPASSEMBLYNAME))ppAssemblyNameObj->lpVtbl->Release)(ppAssemblyNameObj);
    v30 = 0;
  }
}

```

## disassembly

```asm
0x180029524  mov     rax, rsp
0x180029527  mov     [rax+10h], rbx
0x18002952b  mov     [rax+18h], rsi
0x18002952f  mov     [rax+20h], rdi
0x180029533  mov     [rax+8], rcx
0x180029537  push    rbp
0x180029538  push    r12
0x18002953a  push    r13
0x18002953c  push    r14
0x18002953e  push    r15
0x180029540  lea     rbp, [rax-57h]
0x180029544  sub     rsp, 0F0h
0x18002954b  mov     r15, r9
0x18002954e  mov     r14, r8
0x180029551  mov     rbx, rdx
0x180029554  xor     r12d, r12d
0x180029557  mov     [rbp+4Fh+var_B0], r12d
0x18002955b  mov     [rbp+4Fh+var_58], 104h
0x180029562  call    cs:__imp_InitializeFusion
0x180029568  test    eax, eax
0x18002956a  js      loc_1800298A9
0x180029570  mov     [rbp+4Fh+ppAssemblyNameObj], r12
0x180029574  mov     [rbp+4Fh+var_80], r12d
0x180029578  lea     rax, [rbp+4Fh+ppAssemblyNameObj]
0x18002957c  mov     [rbp+4Fh+arg_0], rax
0x180029580  mov     [rbp+4Fh+ppAssemblyNameObj], r12
0x180029584  lea     r13d, [r12+1]
0x180029589  mov     [rbp+4Fh+var_B0], r13d
0x18002958d  xor     r9d, r9d; pvReserved
0x180029590  mov     r8d, r13d; dwFlags
0x180029593  mov     rdx, rbx; szAssemblyName
0x180029596  lea     rcx, [rbp+4Fh+ppAssemblyNameObj]; ppAssemblyNameObj
0x18002959a  call    cs:__imp_CreateAssemblyNameObject
0x1800295a0  test    eax, eax
0x1800295a2  js      loc_1800298B1
0x1800295a8  mov     esi, r13d
0x1800295ab  and     esi, 0FFFFFFFEh
0x1800295ae  mov     [rbp+4Fh+var_B0], esi
0x1800295b1  mov     eax, [rbp+4Fh+var_80]
0x1800295b4  cmp     [rbp+4Fh+ppAssemblyNameObj], r12
0x1800295b8  cmovnz  eax, r13d
0x1800295bc  mov     [rbp+4Fh+var_80], eax
0x1800295bf  mov     [rbp+4Fh+var_98], r12
0x1800295c3  mov     [rbp+4Fh+var_90], r12d
0x1800295c7  lea     rax, [rbp+4Fh+var_98]
0x1800295cb  mov     [rbp+4Fh+arg_0], rax
0x1800295cf  mov     [rbp+4Fh+var_98], r12
0x1800295d3  or      esi, 2
0x1800295d6  mov     [rbp+4Fh+var_B0], esi
0x1800295d9  lea     rdx, [rbp+4Fh+var_98]
0x1800295dd  xor     ecx, ecx
0x1800295df  call    cs:__imp_CreateApplicationContext
0x1800295e5  test    eax, eax
0x1800295e7  js      loc_1800298B9
0x1800295ed  and     esi, 0FFFFFFFDh
0x1800295f0  mov     [rbp+4Fh+var_B0], esi
0x1800295f3  mov     eax, [rbp+4Fh+var_90]
0x1800295f6  mov     rdi, [rbp+4Fh+var_98]
0x1800295fa  test    rdi, rdi
0x1800295fd  cmovnz  eax, r13d
0x180029601  mov     [rbp+4Fh+var_90], eax
0x180029604  mov     rbx, [rdi]
0x180029607  mov     rcx, r14; pbstr
0x18002960a  call    cs:__imp_SysStringLen
0x180029610  mov     r9d, eax
0x180029613  mov     dword ptr [rsp+110h+var_F0], r12d
0x180029618  mov     r8, r14
0x18002961b  lea     rdx, aAppbase_0; "APPBASE"
0x180029622  mov     rcx, rdi
0x180029625  mov     rax, [rbx+28h]
0x180029629  call    cs:__guard_dispatch_icall_fptr
0x18002962f  test    eax, eax
0x180029631  js      loc_1800298C1
0x180029637  mov     [rbp+4Fh+var_A8], r12
0x18002963b  mov     [rbp+4Fh+var_A0], r12d
0x18002963f  lea     rax, [rbp+4Fh+var_A8]
0x180029643  mov     [rbp+4Fh+arg_0], rax
0x180029647  mov     [rbp+4Fh+var_A8], r12
0x18002964b  or      esi, 4
0x18002964e  mov     [rbp+4Fh+var_B0], esi
0x180029651  mov     rdi, [rbp+4Fh+var_98]
0x180029655  mov     rbx, [rbp+4Fh+ppAssemblyNameObj]
0x180029659  lea     r14, ??_7CBindSink@@6B@; const CBindSink::`vftable'
0x180029660  mov     [rbp+4Fh+var_50], r14
0x180029664  mov     [rbp+4Fh+var_48], r13d
0x180029668  mov     [rbp+4Fh+var_44], 80004005h
0x18002966f  lea     rax, [rbp+4Fh+var_A8]
0x180029673  mov     [rbp+4Fh+var_38], rax
0x180029677  xor     r9d, r9d; lpName
0x18002967a  xor     r8d, r8d; bInitialState
0x18002967d  xor     edx, edx; bManualReset
0x18002967f  xor     ecx, ecx; lpEventAttributes
0x180029681  call    cs:__imp_CreateEventW
0x180029687  mov     [rbp+4Fh+hHandle], rax
0x18002968b  mov     [rbp+4Fh+var_78], r12
0x18002968f  mov     [rbp+4Fh+var_70], r12d
0x180029693  lea     rax, [rbp+4Fh+var_78]
0x180029697  mov     [rbp+4Fh+var_30], rax
0x18002969b  mov     [rbp+4Fh+var_78], r12
0x18002969f  or      esi, 8
0x1800296a2  mov     [rbp+4Fh+var_B0], esi
0x1800296a5  mov     rax, [rbx]
0x1800296a8  lea     r8, [rbp+4Fh+var_78]
0x1800296ac  lea     rdx, IID_IAssemblyNameBinder
0x1800296b3  mov     rcx, rbx
0x1800296b6  mov     rax, [rax]
0x1800296b9  call    cs:__guard_dispatch_icall_fptr
0x1800296bf  mov     ebx, eax
0x1800296c1  and     esi, 0FFFFFFF7h
0x1800296c4  mov     [rbp+4Fh+var_B0], esi
0x1800296c7  mov     ecx, [rbp+4Fh+var_70]
0x1800296ca  mov     r10, [rbp+4Fh+var_78]
0x1800296ce  test    r10, r10
0x1800296d1  cmovnz  ecx, r13d
0x1800296d5  mov     [rbp+4Fh+var_70], ecx
0x1800296d8  test    eax, eax
0x1800296da  js      short loc_180029741
0x1800296dc  mov     rax, [r10]
0x1800296df  mov     [rsp+110h+var_C8], r12
0x1800296e4  lea     rcx, [rbp+4Fh+var_A8]
0x1800296e8  mov     [rsp+110h+var_D0], rcx
0x1800296ed  mov     dword ptr [rsp+110h+var_D8], r12d
0x1800296f2  mov     qword ptr [rsp+110h+var_E0], r12
0x1800296f7  mov     [rsp+110h+var_E8], r12
0x1800296fc  mov     [rsp+110h+var_F0], r12
0x180029701  mov     r9, rdi
0x180029704  lea     r8, [rbp+4Fh+var_50]
0x180029708  lea     rdx, IID_IAssembly
0x18002970f  mov     rcx, r10
0x180029712  mov     rax, [rax+18h]
0x180029716  call    cs:__guard_dispatch_icall_fptr
0x18002971c  mov     ebx, eax
0x18002971e  cmp     eax, 8000000Ah
0x180029723  jnz     short loc_180029735
0x180029725  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180029728  mov     rcx, [rbp+4Fh+hHandle]; hHandle
0x18002972c  call    cs:__imp_WaitForSingleObject
0x180029732  mov     ebx, [rbp+4Fh+var_44]
0x180029735  test    ebx, ebx
0x180029737  js      short loc_180029741
0x180029739  cmp     [rbp+4Fh+var_A8], r12
0x18002973d  cmovnz  ebx, r12d
0x180029741  cmp     [rbp+4Fh+var_70], r12d
0x180029745  jz      short loc_180029761
0x180029747  mov     rcx, [rbp+4Fh+var_78]
0x18002974b  test    rcx, rcx
0x18002974e  jz      short loc_18002975D
0x180029750  mov     rax, [rcx]
0x180029753  mov     rax, [rax+10h]
0x180029757  call    cs:__guard_dispatch_icall_fptr
0x18002975d  mov     [rbp+4Fh+var_70], r12d
0x180029761  mov     [rbp+4Fh+var_50], r14
0x180029765  mov     rcx, [rbp+4Fh+hHandle]; hObject
0x180029769  test    rcx, rcx
0x18002976c  jz      short loc_180029774
0x18002976e  call    cs:__imp_CloseHandle
0x180029774  test    ebx, ebx
0x180029776  js      loc_1800298C9
0x18002977c  and     esi, 0FFFFFFFBh
0x18002977f  mov     [rbp+4Fh+var_B0], esi
0x180029782  mov     eax, [rbp+4Fh+var_A0]
0x180029785  cmp     [rbp+4Fh+var_A8], r12
0x180029789  cmovnz  eax, r13d
0x18002978d  mov     [rbp+4Fh+var_A0], eax
0x180029790  mov     [rbp+4Fh+var_68], r12
0x180029794  mov     [rbp+4Fh+var_60], r12d
0x180029798  mov     rcx, [rbp+4Fh+var_A8]
0x18002979c  lea     rax, [rbp+4Fh+var_68]
0x1800297a0  mov     [rbp+4Fh+arg_0], rax
0x1800297a4  mov     [rbp+4Fh+var_68], r12
0x1800297a8  or      esi, 10h
0x1800297ab  mov     [rbp+4Fh+var_B0], esi
0x1800297ae  mov     rax, [rcx]
0x1800297b1  lea     r8, [rbp+4Fh+var_68]
0x1800297b5  lea     rdx, IID_IAssembly
0x1800297bc  mov     rax, [rax]
0x1800297bf  call    cs:__guard_dispatch_icall_fptr
0x1800297c5  test    eax, eax
0x1800297c7  js      loc_1800298D1
0x1800297cd  and     esi, 0FFFFFFEFh
0x1800297d0  mov     [rbp+4Fh+var_B0], esi
0x1800297d3  mov     eax, [rbp+4Fh+var_60]
0x1800297d6  mov     rcx, [rbp+4Fh+var_68]
0x1800297da  test    rcx, rcx
0x1800297dd  cmovnz  eax, r13d
0x1800297e1  mov     [rbp+4Fh+var_60], eax
0x1800297e4  mov     rax, [rcx]
0x1800297e7  lea     r8, [rbp+4Fh+var_58]
0x1800297eb  mov     rdx, r15
0x1800297ee  mov     rax, [rax+38h]
0x1800297f2  call    cs:__guard_dispatch_icall_fptr
0x1800297f8  test    eax, eax
0x1800297fa  js      loc_1800298A1
0x180029800  cmp     [rbp+4Fh+var_60], r12d
0x180029804  jz      short loc_180029820
0x180029806  mov     rcx, [rbp+4Fh+var_68]
0x18002980a  test    rcx, rcx
0x18002980d  jz      short loc_18002981C
0x18002980f  mov     rax, [rcx]
0x180029812  mov     rax, [rax+10h]
0x180029816  call    cs:__guard_dispatch_icall_fptr
0x18002981c  mov     [rbp+4Fh+var_60], r12d
0x180029820  cmp     [rbp+4Fh+var_A0], r12d
0x180029824  jz      short loc_180029840
0x180029826  mov     rcx, [rbp+4Fh+var_A8]
0x18002982a  test    rcx, rcx
0x18002982d  jz      short loc_18002983C
0x18002982f  mov     rax, [rcx]
0x180029832  mov     rax, [rax+10h]
0x180029836  call    cs:__guard_dispatch_icall_fptr
0x18002983c  mov     [rbp+4Fh+var_A0], r12d
0x180029840  cmp     [rbp+4Fh+var_90], r12d
0x180029844  jz      short loc_180029860
0x180029846  mov     rcx, [rbp+4Fh+var_98]
0x18002984a  test    rcx, rcx
0x18002984d  jz      short loc_18002985C
0x18002984f  mov     rax, [rcx]
0x180029852  mov     rax, [rax+10h]
0x180029856  call    cs:__guard_dispatch_icall_fptr
0x18002985c  mov     [rbp+4Fh+var_90], r12d
0x180029860  cmp     [rbp+4Fh+var_80], r12d
0x180029864  jz      short loc_180029880
0x180029866  mov     rcx, [rbp+4Fh+ppAssemblyNameObj]
0x18002986a  test    rcx, rcx
0x18002986d  jz      short loc_18002987C
0x18002986f  mov     rax, [rcx]
0x180029872  mov     rax, [rax+10h]
0x180029876  call    cs:__guard_dispatch_icall_fptr
0x18002987c  mov     [rbp+4Fh+var_80], r12d
0x180029880  lea     r11, [rsp+110h+var_20]
0x180029888  mov     rbx, [r11+38h]
0x18002988c  mov     rsi, [r11+40h]
0x180029890  mov     rdi, [r11+48h]
0x180029894  mov     rsp, r11
0x180029897  pop     r15
0x180029899  pop     r14
0x18002989b  pop     r13
0x18002989d  pop     r12
0x18002989f  pop     rbp
0x1800298a0  retn
0x1800298a1  mov     ecx, eax; int
0x1800298a3  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800298a9  mov     ecx, eax; int
0x1800298ab  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800298b1  mov     ecx, eax; int
0x1800298b3  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800298b9  mov     ecx, eax; int
0x1800298bb  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800298c1  mov     ecx, eax; int
0x1800298c3  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800298c9  mov     ecx, ebx; int
0x1800298cb  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800298d1  mov     ecx, eax; int
0x1800298d3  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
