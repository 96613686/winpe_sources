# Notifier::NotifyThread::CreateEventClasses(IEventObjectChange * *,IEventObjectChange2 * *)

- ea: `0x180027ea0`
- end: `0x180028169`
- name: `?CreateEventClasses@NotifyThread@Notifier@@AEAAXPEAPEAUIEventObjectChange@@PEAPEAUIEventObjectChange2@@@Z`
- size: `713`
- prototype: `void __fastcall(struct CEventSystem2 **this, LPVOID *, LPVOID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180010510`

## callees

- `0x180003d54`
- `0x180008938`
- `0x180027ea0`
- `0x180028170`
- `0x1800281e8`
- `0x180029ad0`
- `0x180035504`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027f3f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027f3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027faf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800280f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027faf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800280f4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027f79`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800280ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027f79`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800280ba`

## string_xrefs

- `0x180027ee3`: `com\complus\src\events\tier2\notify.cpp`
- `0x180027eff`: `com\complus\src\events\tier2\notify.cpp`
- `0x180028029`: `com\complus\src\events\tier2\notify.cpp`
- `0x18002804a`: `com\complus\src\events\tier2\notify.cpp`
- `0x180028066`: `com\complus\src\events\tier2\notify.cpp`

## pseudocode

```c
void __fastcall Notifier::NotifyThread::CreateEventClasses(struct CEventSystem2 **this, LPVOID *a2, LPVOID *a3)
{
  DWORD v6; // edi
  HRESULT v7; // edi
  ObjectChangeFilter *v8; // rax
  struct IMultiInterfaceEventControl *v9; // r8
  ObjectChangeFilter *v10; // rdx
  ObjectChangeFilter *v11; // rcx
  struct CEventSystem2 *v12; // rsi
  struct CEventSystem2 *v13; // rbp
  ObjectChangeFilter *v14; // rax
  struct IMultiInterfaceEventControl *v15; // r8
  ObjectChangeFilter *v16; // rdx
  ObjectChangeFilter *v17; // rcx
  LPVOID ppv; // [rsp+68h] [rbp+10h] BYREF
  LPVOID v19; // [rsp+70h] [rbp+18h] BYREF

  ppv = 0;
  v19 = 0;
  if ( !a2 )
    InternalError(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x183u, 0x80001203, 0x14u);
  if ( !a3 )
    InternalError(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x184u, 0x80001203, 0x14u);
  *a2 = 0;
  *a3 = 0;
  if ( (unsigned int)MemoryPressureExists() )
  {
    v6 = 1010;
    while ( (unsigned int)MemoryPressureExists() )
    {
      Sleep(v6);
      v6 *= 2;
      if ( v6 >= 0xEA60 )
        v6 = 60000;
    }
  }
  v7 = CoCreateInstance(&CLSID_EventObjectChange, 0, 1u, &IID_IEventObjectChange, &ppv);
  if ( v7 >= 0 )
  {
    v7 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, char *))ppv)(
           ppv,
           &IID_IMultiInterfaceEventControl,
           (char *)this + 16);
    if ( v7 >= 0 )
    {
      v8 = (ObjectChangeFilter *)CoTaskMemAlloc(0x80u);
      v10 = v8
          ? ObjectChangeFilter::ObjectChangeFilter(v8, this[8], v9, &CLSID_EventObjectChange, &IID_IEventObjectChange)
          : 0LL;
      this[4] = v10;
      if ( v10 )
      {
        v7 = (*(__int64 (__fastcall **)(struct CEventSystem2 *))(*(_QWORD *)this[2] + 24LL))(this[2]);
        if ( v7 >= 0 )
        {
          *a2 = ppv;
          v7 = CoCreateInstance(&CLSID_EventObjectChange2, 0, 1u, &IID_IEventObjectChange2, &v19);
          if ( v7 >= 0 )
          {
            v7 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, char *))v19)(
                   v19,
                   &IID_IMultiInterfaceEventControl,
                   (char *)this + 24);
            if ( v7 >= 0 )
            {
              v14 = (ObjectChangeFilter *)CoTaskMemAlloc(0x80u);
              v16 = v14
                  ? ObjectChangeFilter::ObjectChangeFilter(
                      v14,
                      this[8],
                      v15,
                      &CLSID_EventObjectChange2,
                      &IID_IEventObjectChange2)
                  : 0LL;
              this[5] = v16;
              if ( v16 )
              {
                v7 = (*(__int64 (__fastcall **)(struct CEventSystem2 *))(*(_QWORD *)this[3] + 24LL))(this[3]);
                if ( v7 >= 0 )
                {
                  *a3 = v19;
                  return;
                }
                v17 = this[5];
                if ( v17 )
                  ObjectChangeFilter::`scalar deleting destructor'(v17);
                this[5] = 0;
              }
            }
          }
        }
        else
        {
          v11 = this[4];
          if ( v11 )
            ObjectChangeFilter::`scalar deleting destructor'(v11);
          this[4] = 0;
        }
      }
    }
  }
  v12 = this[4];
  v13 = this[5];
  Notifier::NotifyThread::ReleaseEventClasses((Notifier::NotifyThread *)this);
  if ( v7 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x1EEu, 0x14u, v7);
  if ( !v12 )
    InternalError(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x1F2u, 0xC0001204, 0x14u);
  if ( !v13 )
    InternalError(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x1F3u, 0xC0001204, 0x14u);
}

```

## disassembly

```asm
0x180027ea0  mov     rax, rsp
0x180027ea3  mov     [rax+8], rbx
0x180027ea7  mov     [rax+20h], rbp
0x180027eab  push    rsi
0x180027eac  push    rdi
0x180027ead  push    r13
0x180027eaf  push    r14
0x180027eb1  push    r15
0x180027eb3  sub     rsp, 30h
0x180027eb7  mov     qword ptr [rax+10h], 0
0x180027ebf  mov     rsi, r8
0x180027ec2  mov     qword ptr [rax+18h], 0
0x180027eca  mov     r14, rdx
0x180027ecd  mov     rbx, rcx
0x180027ed0  mov     edi, 80001203h
0x180027ed5  mov     r13d, 14h
0x180027edb  test    rdx, rdx
0x180027ede  jnz     short loc_180027EF7
0x180027ee0  mov     r9d, r13d; unsigned __int16
0x180027ee3  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x180027eea  mov     r8d, edi; unsigned int
0x180027eed  mov     edx, 183h; unsigned int
0x180027ef2  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180027ef7  test    rsi, rsi
0x180027efa  jnz     short loc_180027F13
0x180027efc  mov     r9d, r13d; unsigned __int16
0x180027eff  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x180027f06  mov     r8d, edi; unsigned int
0x180027f09  mov     edx, 184h; unsigned int
0x180027f0e  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180027f13  mov     qword ptr [r14], 0
0x180027f1a  mov     qword ptr [rsi], 0
0x180027f21  call    ?MemoryPressureExists@@YAHXZ; MemoryPressureExists(void)
0x180027f26  test    eax, eax
0x180027f28  jz      short loc_180027F58
0x180027f2a  mov     edi, 3F2h
0x180027f2f  call    ?MemoryPressureExists@@YAHXZ; MemoryPressureExists(void)
0x180027f34  test    eax, eax
0x180027f36  jz      short loc_180027F58
0x180027f38  mov     ebp, 0EA60h
0x180027f3d  mov     ecx, edi; dwMilliseconds
0x180027f3f  call    cs:__imp_Sleep
0x180027f45  lea     eax, [rdi+rdi]
0x180027f48  cmp     eax, ebp
0x180027f4a  mov     edi, eax
0x180027f4c  cmovnb  edi, ebp
0x180027f4f  call    ?MemoryPressureExists@@YAHXZ; MemoryPressureExists(void)
0x180027f54  test    eax, eax
0x180027f56  jnz     short loc_180027F3D
0x180027f58  xor     edx, edx; pUnkOuter
0x180027f5a  lea     rax, [rsp+58h+arg_8]
0x180027f5f  lea     rbp, IID_IEventObjectChange
0x180027f66  mov     [rsp+58h+ppv], rax; ppv
0x180027f6b  mov     r9, rbp; riid
0x180027f6e  lea     rcx, CLSID_EventObjectChange; rclsid
0x180027f75  lea     r8d, [rdx+1]; dwClsContext
0x180027f79  call    cs:__imp_CoCreateInstance
0x180027f7f  mov     edi, eax
0x180027f81  test    eax, eax
0x180027f83  js      loc_180028012
0x180027f89  mov     rcx, [rsp+58h+arg_8]
0x180027f8e  lea     r8, [rbx+10h]
0x180027f92  lea     rdx, IID_IMultiInterfaceEventControl
0x180027f99  mov     rax, [rcx]
0x180027f9c  mov     rax, [rax]
0x180027f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fa4  mov     edi, eax
0x180027fa6  test    eax, eax
0x180027fa8  js      short loc_180028012
0x180027faa  mov     ecx, 80h; cb
0x180027faf  call    cs:__imp_CoTaskMemAlloc
0x180027fb5  test    rax, rax
0x180027fb8  jz      short loc_180027FD7
0x180027fba  mov     rdx, [rbx+40h]; struct CEventSystem2 *
0x180027fbe  lea     r9, CLSID_EventObjectChange; struct _GUID *
0x180027fc5  mov     rcx, rax; this
0x180027fc8  mov     [rsp+58h+ppv], rbp; struct _GUID *
0x180027fcd  call    ??0ObjectChangeFilter@@QEAA@AEAVCEventSystem2@@PEAUIMultiInterfaceEventControl@@AEBU_GUID@@2@Z; ObjectChangeFilter::ObjectChangeFilter(CEventSystem2 &,IMultiInterfaceEventControl *,_GUID const &,_GUID const &)
0x180027fd2  mov     rdx, rax
0x180027fd5  jmp     short loc_180027FD9
0x180027fd7  xor     edx, edx
0x180027fd9  mov     [rbx+20h], rdx
0x180027fdd  test    rdx, rdx
0x180027fe0  jz      short loc_180028012
0x180027fe2  mov     rcx, [rbx+10h]
0x180027fe6  mov     rax, [rcx]
0x180027fe9  mov     rax, [rax+18h]
0x180027fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ff2  mov     edi, eax
0x180027ff4  test    eax, eax
0x180027ff6  jns     loc_180028091
0x180027ffc  mov     rcx, [rbx+20h]; this
0x180028000  test    rcx, rcx
0x180028003  jz      short loc_18002800A
0x180028005  call    ??_GObjectChangeFilter@@QEAAPEAXI@Z; ObjectChangeFilter::`scalar deleting destructor'(uint)
0x18002800a  mov     qword ptr [rbx+20h], 0
0x180028012  mov     rsi, [rbx+20h]
0x180028016  mov     rcx, rbx; this
0x180028019  mov     rbp, [rbx+28h]
0x18002801d  call    ?ReleaseEventClasses@NotifyThread@Notifier@@AEAAXXZ; Notifier::NotifyThread::ReleaseEventClasses(void)
0x180028022  test    edi, edi
0x180028024  jns     short loc_18002803D
0x180028026  mov     r8d, r13d; unsigned __int16
0x180028029  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x180028030  mov     r9d, edi; int
0x180028033  mov     edx, 1EEh; unsigned int
0x180028038  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18002803d  mov     ebx, 0C0001204h
0x180028042  test    rsi, rsi
0x180028045  jnz     short loc_18002805E
0x180028047  mov     r9d, r13d; unsigned __int16
0x18002804a  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x180028051  mov     r8d, ebx; unsigned int
0x180028054  mov     edx, 1F2h; unsigned int
0x180028059  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18002805e  test    rbp, rbp
0x180028061  jnz     short loc_18002807A
0x180028063  mov     r9d, r13d; unsigned __int16
0x180028066  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18002806d  mov     r8d, ebx; unsigned int
0x180028070  mov     edx, 1F3h; unsigned int
0x180028075  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18002807a  mov     rbx, [rsp+58h+arg_0]
0x18002807f  mov     rbp, [rsp+58h+arg_18]
0x180028084  add     rsp, 30h
0x180028088  pop     r15
0x18002808a  pop     r14
0x18002808c  pop     r13
0x18002808e  pop     rdi
0x18002808f  pop     rsi
0x180028090  retn
0x180028091  mov     rax, [rsp+58h+arg_8]
0x180028096  lea     rbp, IID_IEventObjectChange2
0x18002809d  xor     edx, edx; pUnkOuter
0x18002809f  mov     [r14], rax
0x1800280a2  lea     rax, [rsp+58h+arg_10]
0x1800280a7  mov     r9, rbp; riid
0x1800280aa  lea     rcx, CLSID_EventObjectChange2; rclsid
0x1800280b1  mov     [rsp+58h+ppv], rax; ppv
0x1800280b6  lea     r8d, [rdx+1]; dwClsContext
0x1800280ba  call    cs:__imp_CoCreateInstance
0x1800280c0  mov     edi, eax
0x1800280c2  test    eax, eax
0x1800280c4  js      loc_180028012
0x1800280ca  mov     rcx, [rsp+58h+arg_10]
0x1800280cf  lea     r8, [rbx+18h]
0x1800280d3  lea     rdx, IID_IMultiInterfaceEventControl
0x1800280da  mov     rax, [rcx]
0x1800280dd  mov     rax, [rax]
0x1800280e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280e5  mov     edi, eax
0x1800280e7  test    eax, eax
0x1800280e9  js      loc_180028012
0x1800280ef  mov     ecx, 80h; cb
0x1800280f4  call    cs:__imp_CoTaskMemAlloc
0x1800280fa  test    rax, rax
0x1800280fd  jz      short loc_18002811C
0x1800280ff  mov     rdx, [rbx+40h]; struct CEventSystem2 *
0x180028103  lea     r9, CLSID_EventObjectChange2; struct _GUID *
0x18002810a  mov     rcx, rax; this
0x18002810d  mov     [rsp+58h+ppv], rbp; struct _GUID *
0x180028112  call    ??0ObjectChangeFilter@@QEAA@AEAVCEventSystem2@@PEAUIMultiInterfaceEventControl@@AEBU_GUID@@2@Z; ObjectChangeFilter::ObjectChangeFilter(CEventSystem2 &,IMultiInterfaceEventControl *,_GUID const &,_GUID const &)
0x180028117  mov     rdx, rax
0x18002811a  jmp     short loc_18002811E
0x18002811c  xor     edx, edx
0x18002811e  mov     [rbx+28h], rdx
0x180028122  test    rdx, rdx
0x180028125  jz      loc_180028012
0x18002812b  mov     rcx, [rbx+18h]
0x18002812f  mov     rax, [rcx]
0x180028132  mov     rax, [rax+18h]
0x180028136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002813b  mov     edi, eax
0x18002813d  test    eax, eax
0x18002813f  jns     short loc_18002815C
0x180028141  mov     rcx, [rbx+28h]; this
0x180028145  test    rcx, rcx
0x180028148  jz      short loc_18002814F
0x18002814a  call    ??_GObjectChangeFilter@@QEAAPEAXI@Z; ObjectChangeFilter::`scalar deleting destructor'(uint)
0x18002814f  mov     qword ptr [rbx+28h], 0
0x180028157  jmp     loc_180028012
0x18002815c  mov     rax, [rsp+58h+arg_10]
0x180028161  mov     [rsi], rax
0x180028164  jmp     loc_18002807A
```
