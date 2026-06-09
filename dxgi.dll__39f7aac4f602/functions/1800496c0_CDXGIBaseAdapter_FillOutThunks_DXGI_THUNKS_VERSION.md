# CDXGIBaseAdapter::FillOutThunks(DXGI_THUNKS_VERSION)

- ea: `0x1800496c0`
- end: `0x180049d90`
- name: `?FillOutThunks@CDXGIBaseAdapter@@QEBA?AUDXGI_THUNKS_WIN9@@W4DXGI_THUNKS_VERSION@@@Z`
- size: `1744`
- prototype: `struct DXGI_THUNKS_WIN9 __high(enum DXGI_THUNKS_VERSION)`
- caller_count: `1`
- callee_count: `93`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180049310`

## callees

- `0x180010d40`
- `0x180048314`
- `0x180048398`
- `0x18004841c`
- `0x1800484a0`
- `0x180048524`
- `0x1800485a8`
- `0x18004862c`
- `0x1800486b0`
- `0x180048734`
- `0x1800487b8`
- `0x18004883c`
- `0x1800488c0`
- `0x180048944`
- `0x1800489c8`
- `0x180048a4c`
- `0x180048ad0`
- `0x180048b54`
- `0x180048bd8`
- `0x180048c5c`
- `0x180048ce0`
- `0x180048d64`
- `0x180048de8`
- `0x180048e6c`
- `0x180048ef0`
- `0x180048f74`
- `0x180048ff8`
- `0x18004907c`
- `0x180049100`
- `0x180049184`
- `0x180049208`
- `0x18004928c`
- `0x1800496c0`
- `0x180049d98`
- `0x180049e24`
- `0x180049eb0`
- `0x180049f34`
- `0x180049fb8`
- `0x18004a03c`
- `0x18004a0c0`
- `0x18004a144`
- `0x18004a1c8`
- `0x18004a24c`
- `0x18004a2d0`
- `0x18004a354`
- `0x18004a3d8`
- `0x18004a45c`
- `0x18004a4e0`
- `0x18004a564`
- `0x18004a5e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180049b9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180049b9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800496ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800496ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d3e`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180049d85`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180049d85`

## string_xrefs

- `0x1800496df`: `gdi32.dll`
- `0x180049cbd`: `D3DKMTCreateAllocation`
- `0x180049c9c`: `D3DKMTOpenResource`
- `0x180049b70`: `D3DKMTCreateAllocation2`
- `0x180049b59`: `D3DKMTOpenResource2`

## pseudocode

```c
_QWORD *__fastcall CDXGIBaseAdapter::FillOutThunks(__int64 a1, _QWORD *a2, int a3)
{
  HMODULE v3; // r14
  bool v7; // al
  char v8; // r14
  int v9; // edi
  int v10; // edi
  int v11; // edi
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  _QWORD v15[4]; // [rsp+20h] [rbp-20h] BYREF
  char v16; // [rsp+60h] [rbp+20h] BYREF
  bool v17; // [rsp+70h] [rbp+30h] BYREF

  v3 = *(HMODULE *)(a1 + 232);
  v7 = v3 != GetModuleHandleA("gdi32.dll") && !IsD3D10Level9(v3);
  v8 = 0;
  v17 = v7;
  v16 = 0;
  memset_0(a2, 0, 0x2F8u);
  v15[0] = a1;
  v15[1] = &v16;
  v15[2] = &v17;
  v9 = a3 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( v11 != 1 )
          goto LABEL_7;
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_REGISTERTRIMNOTIFICATION____(
          v15,
          a2 + 79);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_UNREGISTERTRIMNOTIFICATION____(
          v15,
          a2 + 80);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl___D3DDDI_MAKERESIDENT____(v15, a2 + 58);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_EVICT____(v15, a2 + 59);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_const____(
          v15,
          a2 + 60);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU_const____(
          v15,
          a2 + 61);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU_const____(
          v15,
          a2 + 62);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU_const____(
          v15,
          a2 + 63);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2_const____(
          v15,
          a2 + 78);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CREATEPAGINGQUEUE____(v15, a2 + 64);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl___D3DDDI_DESTROYPAGINGQUEUE____(v15, a2 + 65);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_LOCK2____(v15, a2 + 66);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_UNLOCK2_const____(v15, a2 + 67);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_INVALIDATECACHE_const____(
          v15,
          a2 + 68);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA____(
          v15,
          a2 + 88);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl___D3DDDI_RESERVEGPUVIRTUALADDRESS____(
          v15,
          a2 + 70);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl___D3DDDI_MAPGPUVIRTUALADDRESS____(
          v15,
          a2 + 69);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_FREEGPUVIRTUALADDRESS_const____(
          v15,
          a2 + 71);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_UPDATEGPUVIRTUALADDRESS_const____(
          v15,
          a2 + 72);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CREATECONTEXTVIRTUAL____(
          v15,
          a2 + 73);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_SUBMITCOMMAND_const____(
          v15,
          a2 + 74);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME____(
          v15,
          a2 + 76);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2____(
          v15,
          a2 + 75);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_DESTROYALLOCATION2_const____(
          v15,
          a2 + 77);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_QUERYVIDEOMEMORYINFO____(
          v15,
          a2 + 81);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CHANGEVIDEOMMEMORYRESERVATION_const____(
          v15,
          a2 + 82);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_RECLAIMALLOCATIONS2____(
          v15,
          a2 + 85);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_PRESENT_MULTIPLANE_OVERLAY2_const____(
          v15,
          a2 + 86);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2____(
          v15,
          a2 + 87);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_SETSTABLEPOWERSTATE_const____(
          v15,
          a2 + 89);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_QUERYCLOCKCALIBRATION____(
          v15,
          a2 + 90);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_MARKDEVICEASERROR____(v15, a2 + 91);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_FLUSHHEAPTRANSITIONS____(
          v15,
          a2 + 92);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl___D3DDDI_UPDATEALLOCPROPERTY____(
          v15,
          a2 + 93);
        lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_GETALLOCATIONPRIORITY_const____(
          v15,
          a2 + 94);
      }
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_OFFERALLOCATIONS_const____(
        v15,
        a2 + 40);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_RECLAIMALLOCATIONS_const____(
        v15,
        a2 + 41);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_RELEASEKEYEDMUTEX2____(v15, a2 + 45);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_ACQUIREKEYEDMUTEX2____(v15, a2 + 44);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_OPENKEYEDMUTEX2____(v15, a2 + 43);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CREATEKEYEDMUTEX2____(v15, a2 + 42);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_OUTPUTDUPLPRESENT_const____(
        v15,
        a2 + 46);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE____(
        v15,
        a2 + 47);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl___unsigned_int_unsigned_int_const____OBJECT_ATTRIBUTES___unsigned_long_void______(
        v15,
        a2 + 48);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_OPENNTHANDLEFROMNAME____(
        v15,
        a2 + 49);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_OPENRESOURCEFROMNTHANDLE____(
        v15,
        a2 + 50);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_PINDIRECTFLIPRESOURCES_const____(
        v15,
        a2 + 51);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_UNPINDIRECTFLIPRESOURCES_const____(
        v15,
        a2 + 52);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY_const____(
        v15,
        a2 + 53);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY____(
        v15,
        a2 + 54);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_OPENSYNCOBJECTFROMNTHANDLE____(
        v15,
        a2 + 55);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl___D3DKMT_PRESENT_MULTIPLANE_OVERLAY_const____(
        v15,
        a2 + 56);
      lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT____(
        v15,
        a2 + 57);
    }
    lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2_const____(
      v15,
      a2 + 38);
    lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2_const____(
      v15,
      a2 + 37);
    lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_OPENSYNCHRONIZATIONOBJECT____(
      v15,
      a2 + 36);
    lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CREATESYNCHRONIZATIONOBJECT2____(
      v15,
      a2 + 35);
    lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_RELEASEKEYEDMUTEX____(v15, a2 + 34);
    lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_ACQUIREKEYEDMUTEX____(v15, a2 + 33);
    lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_DESTROYKEYEDMUTEX_const____(
      v15,
      a2 + 32);
    lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_OPENKEYEDMUTEX____(v15, a2 + 31);
    lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CREATEKEYEDMUTEX____(v15, a2 + 30);
    lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_OPENRESOURCE____(
      v15,
      a2 + 29,
      "D3DKMTOpenResource2");
    lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CREATEALLOCATION____(
      v15,
      a2 + 28,
      "D3DKMTCreateAllocation2");
    lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CONFIGURESHAREDRESOURCE_const____(
      v15,
      a2 + 39);
  }
  ProcAddress = GetProcAddress(*(HMODULE *)(a1 + 232), "D3DKMTSetQueuedLimit");
  a2[27] = ProcAddress;
  if ( !ProcAddress && !v17 )
    RaiseFailFastException(0, 0, 1u);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_GETMULTISAMPLEMETHODLIST____(
    v15,
    a2 + 26);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_QUERYADAPTERINFO_const____(v15, a2 + 25);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT_const____(
    v15,
    a2 + 24);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_DESTROYSYNCHRONIZATIONOBJECT_const____(
    v15,
    a2 + 23);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CREATESYNCHRONIZATIONOBJECT____(
    v15,
    a2 + 22);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_DESTROYCONTEXT_const____(v15, a2 + 21);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CREATECONTEXT____(v15, a2 + 20);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_GETCONTEXTSCHEDULINGPRIORITY____(
    v15,
    a2 + 19);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_SETCONTEXTSCHEDULINGPRIORITY_const____(
    v15,
    a2 + 18);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_PRESENT____(v15, a2 + 17);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_DESTROYDEVICE_const____(v15, a2 + 16);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CREATEDEVICE____(v15, a2 + 15);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_QUERYALLOCATIONRESIDENCY_const____(
    v15,
    a2 + 14);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_SETALLOCATIONPRIORITY_const____(
    v15,
    a2 + 13);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_DESTROYALLOCATION_const____(v15, a2 + 12);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_OPENRESOURCE____(
    v15,
    a2 + 11,
    "D3DKMTOpenResource");
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_QUERYRESOURCEINFO____(v15, a2 + 10);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_CREATEALLOCATION____(
    v15,
    a2 + 9,
    "D3DKMTCreateAllocation");
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_GETDEVICESTATE____(v15, a2 + 8);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_SETDISPLAYMODE_const____(v15, a2 + 7);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_SIGNALSYNCHRONIZATIONOBJECT_const____(
    v15,
    a2 + 6);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_WAITFORSYNCHRONIZATIONOBJECT_const____(
    v15,
    a2 + 5);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_ESCAPE_const____(v15, a2 + 4);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_UNLOCK_const____(v15, a2 + 3);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_LOCK____(v15, a2 + 2);
  lambda_f93aa6c630286660b09bacfb3e5cb883_::operator()_long____cdecl____D3DKMT_RENDER____(v15, a2 + 1);
  v8 = v16;
LABEL_7:
  *(_DWORD *)a2 = *(_DWORD *)(a1 + 744);
  if ( v8 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    DXGIThrowFailure(LastError);
  }
  return a2;
}

```

## disassembly

```asm
0x1800496c0  mov     [rsp-18h+arg_8], rbx
0x1800496c5  mov     [rsp-18h+arg_18], rsi
0x1800496ca  push    rbp
0x1800496cb  push    rdi
0x1800496cc  push    r14
0x1800496ce  mov     rbp, rsp
0x1800496d1  sub     rsp, 40h
0x1800496d5  mov     r14, [rcx+0E8h]
0x1800496dc  mov     rsi, rcx
0x1800496df  lea     rcx, ModuleName; "gdi32.dll"
0x1800496e6  mov     edi, r8d
0x1800496e9  mov     rbx, rdx
0x1800496ec  call    cs:__imp_GetModuleHandleA
0x1800496f2  cmp     r14, rax
0x1800496f5  jnz     loc_180049D5C
0x1800496fb  xor     al, al
0x1800496fd  xor     r14b, r14b
0x180049700  mov     [rbp+arg_10], al
0x180049703  xor     edx, edx; Val
0x180049705  mov     [rbp+arg_0], r14b
0x180049709  mov     r8d, 2F8h; Size
0x18004970f  mov     rcx, rbx; void *
0x180049712  call    memset_0
0x180049717  mov     [rbp+var_20], rsi
0x18004971b  lea     rax, [rbp+arg_0]
0x18004971f  mov     [rbp+var_18], rax
0x180049723  lea     rax, [rbp+arg_10]
0x180049727  mov     [rbp+var_10], rax
0x18004972b  sub     edi, 1
0x18004972e  jz      loc_180049B90
0x180049734  sub     edi, 1
0x180049737  jz      loc_180049AC2
0x18004973d  sub     edi, 1
0x180049740  jz      loc_1800499A2
0x180049746  cmp     edi, 1
0x180049749  jz      short loc_180049772
0x18004974b  mov     eax, [rsi+2E8h]
0x180049751  mov     [rbx], eax
0x180049753  test    r14b, r14b
0x180049756  jnz     loc_180049D3E
0x18004975c  mov     rsi, [rsp+40h+arg_18]
0x180049761  mov     rax, rbx
0x180049764  mov     rbx, [rsp+40h+arg_8]
0x180049769  add     rsp, 40h
0x18004976d  pop     r14
0x18004976f  pop     rdi
0x180049770  pop     rbp
0x180049771  retn
0x180049772  lea     rdx, [rbx+278h]
0x180049779  lea     rcx, [rbp+var_20]
0x18004977d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_REGISTERTRIMNOTIFICATION____
0x180049782  lea     rdx, [rbx+280h]
0x180049789  lea     rcx, [rbp+var_20]
0x18004978d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_UNREGISTERTRIMNOTIFICATION____
0x180049792  lea     rdx, [rbx+1D0h]
0x180049799  lea     rcx, [rbp+var_20]
0x18004979d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl___D3DDDI_MAKERESIDENT____
0x1800497a2  lea     rdx, [rbx+1D8h]
0x1800497a9  lea     rcx, [rbp+var_20]
0x1800497ad  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_EVICT____
0x1800497b2  lea     rdx, [rbx+1E0h]
0x1800497b9  lea     rcx, [rbp+var_20]
0x1800497bd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_const____
0x1800497c2  lea     rdx, [rbx+1E8h]
0x1800497c9  lea     rcx, [rbp+var_20]
0x1800497cd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU_const____
0x1800497d2  lea     rdx, [rbx+1F0h]
0x1800497d9  lea     rcx, [rbp+var_20]
0x1800497dd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU_const____
0x1800497e2  lea     rdx, [rbx+1F8h]
0x1800497e9  lea     rcx, [rbp+var_20]
0x1800497ed  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU_const____
0x1800497f2  lea     rdx, [rbx+270h]
0x1800497f9  lea     rcx, [rbp+var_20]
0x1800497fd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2_const____
0x180049802  lea     rdx, [rbx+200h]
0x180049809  lea     rcx, [rbp+var_20]
0x18004980d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_CREATEPAGINGQUEUE____
0x180049812  lea     rdx, [rbx+208h]
0x180049819  lea     rcx, [rbp+var_20]
0x18004981d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl___D3DDDI_DESTROYPAGINGQUEUE____
0x180049822  lea     rdx, [rbx+210h]
0x180049829  lea     rcx, [rbp+var_20]
0x18004982d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_LOCK2____
0x180049832  lea     rdx, [rbx+218h]
0x180049839  lea     rcx, [rbp+var_20]
0x18004983d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_UNLOCK2_const____
0x180049842  lea     rdx, [rbx+220h]
0x180049849  lea     rcx, [rbp+var_20]
0x18004984d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_INVALIDATECACHE_const____
0x180049852  lea     rdx, [rbx+2C0h]
0x180049859  lea     rcx, [rbp+var_20]
0x18004985d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA____
0x180049862  lea     rdx, [rbx+230h]
0x180049869  lea     rcx, [rbp+var_20]
0x18004986d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl___D3DDDI_RESERVEGPUVIRTUALADDRESS____
0x180049872  lea     rdx, [rbx+228h]
0x180049879  lea     rcx, [rbp+var_20]
0x18004987d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl___D3DDDI_MAPGPUVIRTUALADDRESS____
0x180049882  lea     rdx, [rbx+238h]
0x180049889  lea     rcx, [rbp+var_20]
0x18004988d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_FREEGPUVIRTUALADDRESS_const____
0x180049892  lea     rdx, [rbx+240h]
0x180049899  lea     rcx, [rbp+var_20]
0x18004989d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_UPDATEGPUVIRTUALADDRESS_const____
0x1800498a2  lea     rdx, [rbx+248h]
0x1800498a9  lea     rcx, [rbp+var_20]
0x1800498ad  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_CREATECONTEXTVIRTUAL____
0x1800498b2  lea     rdx, [rbx+250h]
0x1800498b9  lea     rcx, [rbp+var_20]
0x1800498bd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_SUBMITCOMMAND_const____
0x1800498c2  lea     rdx, [rbx+260h]
0x1800498c9  lea     rcx, [rbp+var_20]
0x1800498cd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME____
0x1800498d2  lea     rdx, [rbx+258h]
0x1800498d9  lea     rcx, [rbp+var_20]
0x1800498dd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2____
0x1800498e2  lea     rdx, [rbx+268h]
0x1800498e9  lea     rcx, [rbp+var_20]
0x1800498ed  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_DESTROYALLOCATION2_const____
0x1800498f2  lea     rdx, [rbx+288h]
0x1800498f9  lea     rcx, [rbp+var_20]
0x1800498fd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_QUERYVIDEOMEMORYINFO____
0x180049902  lea     rdx, [rbx+290h]
0x180049909  lea     rcx, [rbp+var_20]
0x18004990d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_CHANGEVIDEOMMEMORYRESERVATION_const____
0x180049912  lea     rdx, [rbx+2A8h]
0x180049919  lea     rcx, [rbp+var_20]
0x18004991d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_RECLAIMALLOCATIONS2____
0x180049922  lea     rdx, [rbx+2B0h]
0x180049929  lea     rcx, [rbp+var_20]
0x18004992d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_PRESENT_MULTIPLANE_OVERLAY2_const____
0x180049932  lea     rdx, [rbx+2B8h]
0x180049939  lea     rcx, [rbp+var_20]
0x18004993d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT2____
0x180049942  lea     rdx, [rbx+2C8h]
0x180049949  lea     rcx, [rbp+var_20]
0x18004994d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_SETSTABLEPOWERSTATE_const____
0x180049952  lea     rdx, [rbx+2D0h]
0x180049959  lea     rcx, [rbp+var_20]
0x18004995d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_QUERYCLOCKCALIBRATION____
0x180049962  lea     rdx, [rbx+2D8h]
0x180049969  lea     rcx, [rbp+var_20]
0x18004996d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_MARKDEVICEASERROR____
0x180049972  lea     rdx, [rbx+2E0h]
0x180049979  lea     rcx, [rbp+var_20]
0x18004997d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_FLUSHHEAPTRANSITIONS____
0x180049982  lea     rdx, [rbx+2E8h]
0x180049989  lea     rcx, [rbp+var_20]
0x18004998d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl___D3DDDI_UPDATEALLOCPROPERTY____
0x180049992  lea     rdx, [rbx+2F0h]
0x180049999  lea     rcx, [rbp+var_20]
0x18004999d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_GETALLOCATIONPRIORITY_const____
0x1800499a2  lea     rdx, [rbx+140h]
0x1800499a9  lea     rcx, [rbp+var_20]
0x1800499ad  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_OFFERALLOCATIONS_const____
0x1800499b2  lea     rdx, [rbx+148h]
0x1800499b9  lea     rcx, [rbp+var_20]
0x1800499bd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_RECLAIMALLOCATIONS_const____
0x1800499c2  lea     rdx, [rbx+168h]
0x1800499c9  lea     rcx, [rbp+var_20]
0x1800499cd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_RELEASEKEYEDMUTEX2____
0x1800499d2  lea     rdx, [rbx+160h]
0x1800499d9  lea     rcx, [rbp+var_20]
0x1800499dd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_ACQUIREKEYEDMUTEX2____
0x1800499e2  lea     rdx, [rbx+158h]
0x1800499e9  lea     rcx, [rbp+var_20]
0x1800499ed  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_OPENKEYEDMUTEX2____
0x1800499f2  lea     rdx, [rbx+150h]
0x1800499f9  lea     rcx, [rbp+var_20]
0x1800499fd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_CREATEKEYEDMUTEX2____
0x180049a02  lea     rdx, [rbx+170h]
0x180049a09  lea     rcx, [rbp+var_20]
0x180049a0d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_OUTPUTDUPLPRESENT_const____
0x180049a12  lea     rdx, [rbx+178h]
0x180049a19  lea     rcx, [rbp+var_20]
0x180049a1d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE____
0x180049a22  lea     rdx, [rbx+180h]
0x180049a29  lea     rcx, [rbp+var_20]
0x180049a2d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl___unsigned_int_unsigned_int_const____OBJECT_ATTRIBUTES___unsigned_long_void______
0x180049a32  lea     rdx, [rbx+188h]
0x180049a39  lea     rcx, [rbp+var_20]
0x180049a3d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_OPENNTHANDLEFROMNAME____
0x180049a42  lea     rdx, [rbx+190h]
0x180049a49  lea     rcx, [rbp+var_20]
0x180049a4d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_OPENRESOURCEFROMNTHANDLE____
0x180049a52  lea     rdx, [rbx+198h]
0x180049a59  lea     rcx, [rbp+var_20]
0x180049a5d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_PINDIRECTFLIPRESOURCES_const____
0x180049a62  lea     rdx, [rbx+1A0h]
0x180049a69  lea     rcx, [rbp+var_20]
0x180049a6d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_UNPINDIRECTFLIPRESOURCES_const____
0x180049a72  lea     rdx, [rbx+1A8h]
0x180049a79  lea     rcx, [rbp+var_20]
0x180049a7d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY_const____
0x180049a82  lea     rdx, [rbx+1B0h]
0x180049a89  lea     rcx, [rbp+var_20]
0x180049a8d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY____
0x180049a92  lea     rdx, [rbx+1B8h]
0x180049a99  lea     rcx, [rbp+var_20]
0x180049a9d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_OPENSYNCOBJECTFROMNTHANDLE____
0x180049aa2  lea     rdx, [rbx+1C0h]
0x180049aa9  lea     rcx, [rbp+var_20]
0x180049aad  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl___D3DKMT_PRESENT_MULTIPLANE_OVERLAY_const____
0x180049ab2  lea     rdx, [rbx+1C8h]
0x180049ab9  lea     rcx, [rbp+var_20]
0x180049abd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT____
0x180049ac2  lea     rdx, [rbx+130h]
0x180049ac9  lea     rcx, [rbp+var_20]
0x180049acd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2_const____
0x180049ad2  lea     rdx, [rbx+128h]
0x180049ad9  lea     rcx, [rbp+var_20]
0x180049add  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2_const____
0x180049ae2  lea     rdx, [rbx+120h]
0x180049ae9  lea     rcx, [rbp+var_20]
0x180049aed  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_OPENSYNCHRONIZATIONOBJECT____
0x180049af2  lea     rdx, [rbx+118h]
0x180049af9  lea     rcx, [rbp+var_20]
0x180049afd  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_CREATESYNCHRONIZATIONOBJECT2____
0x180049b02  lea     rdx, [rbx+110h]
0x180049b09  lea     rcx, [rbp+var_20]
0x180049b0d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_RELEASEKEYEDMUTEX____
0x180049b12  lea     rdx, [rbx+108h]
0x180049b19  lea     rcx, [rbp+var_20]
0x180049b1d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_ACQUIREKEYEDMUTEX____
0x180049b22  lea     rdx, [rbx+100h]
0x180049b29  lea     rcx, [rbp+var_20]
0x180049b2d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_DESTROYKEYEDMUTEX_const____
0x180049b32  lea     rdx, [rbx+0F8h]
0x180049b39  lea     rcx, [rbp+var_20]
0x180049b3d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_OPENKEYEDMUTEX____
0x180049b42  lea     rdx, [rbx+0F0h]
0x180049b49  lea     rcx, [rbp+var_20]
0x180049b4d  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_CREATEKEYEDMUTEX____
0x180049b52  lea     rdx, [rbx+0E8h]
0x180049b59  lea     r8, aD3dkmtopenreso; "D3DKMTOpenResource2"
0x180049b60  lea     rcx, [rbp+var_20]
0x180049b64  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_OPENRESOURCE____
0x180049b69  lea     rdx, [rbx+0E0h]
0x180049b70  lea     r8, aD3dkmtcreateal_0; "D3DKMTCreateAllocation2"
0x180049b77  lea     rcx, [rbp+var_20]
0x180049b7b  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_CREATEALLOCATION____
0x180049b80  lea     rdx, [rbx+138h]
0x180049b87  lea     rcx, [rbp+var_20]
0x180049b8b  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_CONFIGURESHAREDRESOURCE_const____
0x180049b90  mov     rcx, [rsi+0E8h]; hModule
0x180049b97  lea     rdx, aD3dkmtsetqueue; "D3DKMTSetQueuedLimit"
0x180049b9e  call    cs:__imp_GetProcAddress
0x180049ba4  mov     [rbx+0D8h], rax
0x180049bab  test    rax, rax
0x180049bae  jz      loc_180049D73
0x180049bb4  lea     rdx, [rbx+0D0h]
0x180049bbb  lea     rcx, [rbp+var_20]
0x180049bbf  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_GETMULTISAMPLEMETHODLIST____
0x180049bc4  lea     rdx, [rbx+0C8h]
0x180049bcb  lea     rcx, [rbp+var_20]
0x180049bcf  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_QUERYADAPTERINFO_const____
0x180049bd4  lea     rdx, [rbx+0C0h]
0x180049bdb  lea     rcx, [rbp+var_20]
0x180049bdf  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT_const____
0x180049be4  lea     rdx, [rbx+0B8h]
0x180049beb  lea     rcx, [rbp+var_20]
0x180049bef  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_DESTROYSYNCHRONIZATIONOBJECT_const____
0x180049bf4  lea     rdx, [rbx+0B0h]
0x180049bfb  lea     rcx, [rbp+var_20]
0x180049bff  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_CREATESYNCHRONIZATIONOBJECT____
0x180049c04  lea     rdx, [rbx+0A8h]
0x180049c0b  lea     rcx, [rbp+var_20]
0x180049c0f  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_DESTROYCONTEXT_const____
0x180049c14  lea     rdx, [rbx+0A0h]
0x180049c1b  lea     rcx, [rbp+var_20]
0x180049c1f  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_CREATECONTEXT____
0x180049c24  lea     rdx, [rbx+98h]
0x180049c2b  lea     rcx, [rbp+var_20]
0x180049c2f  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_GETCONTEXTSCHEDULINGPRIORITY____
0x180049c34  lea     rdx, [rbx+90h]
0x180049c3b  lea     rcx, [rbp+var_20]
0x180049c3f  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_SETCONTEXTSCHEDULINGPRIORITY_const____
0x180049c44  lea     rdx, [rbx+88h]
0x180049c4b  lea     rcx, [rbp+var_20]
0x180049c4f  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_PRESENT____
0x180049c54  lea     rdx, [rbx+80h]
0x180049c5b  lea     rcx, [rbp+var_20]
0x180049c5f  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_DESTROYDEVICE_const____
0x180049c64  lea     rdx, [rbx+78h]
0x180049c68  lea     rcx, [rbp+var_20]
0x180049c6c  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_CREATEDEVICE____
0x180049c71  lea     rdx, [rbx+70h]
0x180049c75  lea     rcx, [rbp+var_20]
0x180049c79  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_QUERYALLOCATIONRESIDENCY_const____
0x180049c7e  lea     rdx, [rbx+68h]
0x180049c82  lea     rcx, [rbp+var_20]
0x180049c86  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_SETALLOCATIONPRIORITY_const____
0x180049c8b  lea     rdx, [rbx+60h]
0x180049c8f  lea     rcx, [rbp+var_20]
0x180049c93  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_DESTROYALLOCATION_const____
0x180049c98  lea     rdx, [rbx+58h]
0x180049c9c  lea     r8, aD3dkmtopenreso_1; "D3DKMTOpenResource"
0x180049ca3  lea     rcx, [rbp+var_20]
0x180049ca7  call    _lambda_f93aa6c630286660b09bacfb3e5cb883___operator___long____cdecl____D3DKMT_OPENRESOURCE____
  ... truncated ...
```
