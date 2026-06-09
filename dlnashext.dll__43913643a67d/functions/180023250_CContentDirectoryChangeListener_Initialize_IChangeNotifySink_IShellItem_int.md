# CContentDirectoryChangeListener::Initialize(IChangeNotifySink *,IShellItem *,int)

- ea: `0x180023250`
- end: `0x18002332a`
- name: `?Initialize@CContentDirectoryChangeListener@@UEAAJPEAUIChangeNotifySink@@PEAUIShellItem@@H@Z`
- size: `218`
- prototype: `int(CContentDirectoryChangeListener *__hidden this, struct IChangeNotifySink *, struct IShellItem *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007840`
- `0x180008430`
- `0x18001a2f8`
- `0x180023250`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002328a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800232f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002328a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800232f2`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x180023296`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x180023296`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800232dd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800232dd`

## pseudocode

```c
__int64 __fastcall CContentDirectoryChangeListener::Initialize(
        CContentDirectoryChangeListener *this,
        struct IChangeNotifySink *a2,
        IUnknown *a3)
{
  IUnknown *v3; // r14
  HRESULT v5; // ebx
  void *v6; // rcx
  LPCWCH *v7; // rsi
  WCHAR *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  _BYTE v12[56]; // [rsp+30h] [rbp-38h] BYREF

  v3 = a3;
  LOBYTE(a3) = 1;
  ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(v12, (char *)this + 24, a3);
  v5 = 0;
  if ( !*((_DWORD *)this + 16) )
  {
    v6 = (void *)*((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = 0;
    CoTaskMemFree(v6);
    v5 = SHGetIDListFromObject(v3, (LPITEMIDLIST *)this + 10);
    if ( v5 >= 0 )
    {
      v7 = (LPCWCH *)((char *)this + 88);
      v5 = ((__int64 (__fastcall *)(IUnknown *, __int64, char *))v3->lpVtbl[1].Release)(
             v3,
             2147581953LL,
             (char *)this + 88);
      if ( v5 >= 0 )
      {
        if ( CompareStringOrdinal(*v7, 5, L"uuid:", 5, 1) != 2
          || (v8 = (WCHAR *)*v7,
              *v7 = 0,
              CoTaskMemFree(v8),
              v5 = _AllocString<CTCoAllocPolicy>(v10, v9, L"0", (char *)this + 88),
              v5 >= 0) )
        {
          *((_DWORD *)this + 16) = 2;
        }
      }
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180023250  push    rbx
0x180023252  push    rsi
0x180023253  push    rdi
0x180023254  push    r14
0x180023256  sub     rsp, 48h
0x18002325a  mov     r14, r8
0x18002325d  lea     rdx, [rcx+18h]
0x180023261  mov     rdi, rcx
0x180023264  mov     r8b, 1
0x180023267  lea     rcx, [rsp+68h+var_38]
0x18002326c  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x180023271  xor     ebx, ebx
0x180023273  cmp     [rdi+40h], ebx
0x180023276  jnz     loc_180023314
0x18002327c  lea     rbx, [rdi+50h]
0x180023280  mov     rcx, [rbx]; pv
0x180023283  mov     qword ptr [rbx], 0
0x18002328a  call    cs:__imp_CoTaskMemFree
0x180023290  mov     rdx, rbx; ppidl
0x180023293  mov     rcx, r14; punk
0x180023296  call    cs:__imp_SHGetIDListFromObject
0x18002329c  mov     ebx, eax
0x18002329e  test    eax, eax
0x1800232a0  js      short loc_180023314
0x1800232a2  mov     rax, [r14]
0x1800232a5  lea     rsi, [rdi+58h]
0x1800232a9  mov     r8, rsi
0x1800232ac  mov     edx, 80018001h
0x1800232b1  mov     rcx, r14
0x1800232b4  mov     rax, [rax+28h]
0x1800232b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232bd  mov     ebx, eax
0x1800232bf  test    eax, eax
0x1800232c1  js      short loc_180023314
0x1800232c3  mov     rcx, [rsi]; lpString1
0x1800232c6  lea     r8, aUuid; "uuid:"
0x1800232cd  mov     edx, 5; cchCount1
0x1800232d2  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x1800232da  mov     r9d, edx; cchCount2
0x1800232dd  call    cs:__imp_CompareStringOrdinal
0x1800232e3  cmp     eax, 2
0x1800232e6  jnz     short loc_18002330D
0x1800232e8  mov     rcx, [rsi]; pv
0x1800232eb  mov     qword ptr [rsi], 0
0x1800232f2  call    cs:__imp_CoTaskMemFree
0x1800232f8  mov     r9, rsi
0x1800232fb  lea     r8, psz; "0"
0x180023302  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180023307  mov     ebx, eax
0x180023309  test    eax, eax
0x18002330b  js      short loc_180023314
0x18002330d  mov     dword ptr [rdi+40h], 2
0x180023314  lea     rcx, [rsp+68h+var_38]
0x180023319  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002331e  mov     eax, ebx
0x180023320  add     rsp, 48h
0x180023324  pop     r14
0x180023326  pop     rdi
0x180023327  pop     rsi
0x180023328  pop     rbx
0x180023329  retn
```
