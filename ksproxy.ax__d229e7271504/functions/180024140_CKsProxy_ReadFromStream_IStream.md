# CKsProxy::ReadFromStream(IStream *)

- ea: `0x180024140`
- end: `0x1800243f8`
- name: `?ReadFromStream@CKsProxy@@UEAAJPEAUIStream@@@Z`
- size: `696`
- prototype: `__int64 __fastcall(CKsProxy *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180009c4c`
- `0x18000c93c`
- `0x18000c9f0`
- `0x18001f620`
- `0x18001ffb0`
- `0x180024140`
- `0x180045010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180024320`
- `ole32!CoTaskMemAlloc` at `0x180024320`
- `ole32!CoCreateInstance` at `0x1800241c2`
- `ole32!CoCreateInstance` at `0x1800241c2`

## pseudocode

```c
__int64 __fastcall CKsProxy::ReadFromStream(CKsProxy *this, struct IStream *a2)
{
  bool v2; // zf
  HRESULT v6; // ebx
  IStream_vtbl *v7; // rax
  IStream_vtbl *v8; // rax
  CKsProxy *v9; // rcx
  IKsObject_vtbl *v10; // rsi
  struct CBasePin *Release; // r15
  int PinFactoryId; // eax
  int v13; // [rsp+30h] [rbp-59h] BYREF
  int v14; // [rsp+34h] [rbp-55h] BYREF
  __int64 v15; // [rsp+38h] [rbp-51h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-49h] BYREF
  struct _AMMediaType v17; // [rsp+50h] [rbp-39h] BYREF

  v2 = this->m_CritSec.DebugInfo == 0;
  ppv = 0;
  if ( !v2 )
    return 2147943647LL;
  if ( (_AMOVIESETUP_FILTER *)LODWORD(this->m_pUnknown) > this->GetSetupData(this) )
    return 2147942413LL;
  v6 = CoCreateInstance(&CLSID_CDeviceMoniker, 0, 0x401u, &IID_IPersistStream, &ppv);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, struct IStream *))(*(_QWORD *)ppv + 40LL))(ppv, a2);
    if ( v6 >= 0 )
    {
      v15 = 0;
      v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPropertyBag, &v15);
      if ( v6 >= 0 )
      {
        v6 = ((__int64 (__fastcall *)(IBaseFilter *, __int64, _QWORD))this->Pause)(&this->IBaseFilter, v15, 0);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v6 >= 0 && LODWORD(this->m_pUnknown) == 1 )
    {
      v7 = a2->__vftable;
      v14 = 0;
      v13 = 0;
      v6 = v7->Read(a2, &v13, 4u, (unsigned int *)&v14);
      if ( v6 >= 0 )
      {
        if ( v14 == 4 )
        {
          do
          {
            if ( !v13 )
              break;
            v8 = a2->__vftable;
            LODWORD(v15) = 0;
            v6 = v8->Read(a2, &v15, 4u, (unsigned int *)&v14);
            if ( v6 < 0 )
              break;
            v13 -= v14;
            memset_0((void *)&v17, 0, sizeof(v17));
            v6 = a2->Read(a2, (void *)&v17, 88u, (unsigned int *)&v14);
            if ( v6 < 0 )
              break;
            v13 -= v14;
            v17.pbFormat = (unsigned __int8 *)CoTaskMemAlloc(v17.cbFormat);
            if ( !v17.pbFormat )
              return (unsigned int)-2147024882;
            v6 = a2->Read(a2, v17.pbFormat, v17.cbFormat, (unsigned int *)&v14);
            if ( v6 < 0 )
            {
              FreeMediaType(&v17);
              return (unsigned int)v6;
            }
            v13 -= v14;
            v10 = this->IKsObject::IUnknown::__vftable;
            while ( v10 )
            {
              Release = (struct CBasePin *)v10->Release;
              v10 = (IKsObject_vtbl *)v10->AddRef;
              if ( !CKsProxy::GetPinHandle(v9, Release) )
              {
                PinFactoryId = CKsProxy::GetPinFactoryId(v9, Release);
                if ( (_DWORD)v15 == PinFactoryId )
                {
                  v6 = Release->Connect(&Release->IPin, 0, &v17);
                  break;
                }
              }
            }
            FreeMediaType(&v17);
          }
          while ( v6 >= 0 );
        }
        else
        {
          return (unsigned int)-2147220925;
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180024140  mov     [rsp-8+arg_10], rbx
0x180024145  push    rbp
0x180024146  push    rsi
0x180024147  push    rdi
0x180024148  push    r14
0x18002414a  push    r15
0x18002414c  lea     rbp, [rsp-37h]
0x180024151  sub     rsp, 0C0h
0x180024158  mov     rax, cs:__security_cookie
0x18002415f  xor     rax, rsp
0x180024162  mov     [rbp+57h+var_30], rax
0x180024166  cmp     qword ptr [rcx+0F8h], 0
0x18002416e  mov     r14, rdx
0x180024171  mov     rdi, rcx
0x180024174  mov     [rbp+57h+var_A0], 0
0x18002417c  jz      short loc_180024188
0x18002417e  mov     eax, 800704DFh
0x180024183  jmp     loc_1800243D4
0x180024188  mov     rax, [rcx]
0x18002418b  mov     rax, [rax+40h]
0x18002418f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024194  cmp     [rdi+8], eax
0x180024197  jbe     short loc_1800241A3
0x180024199  mov     eax, 8007000Dh
0x18002419e  jmp     loc_1800243D4
0x1800241a3  lea     rax, [rbp+57h+var_A0]
0x1800241a7  xor     edx, edx; pUnkOuter
0x1800241a9  lea     r9, IID_IPersistStream; riid
0x1800241b0  mov     [rsp+0E0h+ppv], rax; ppv
0x1800241b5  mov     r8d, 401h; dwClsContext
0x1800241bb  lea     rcx, CLSID_CDeviceMoniker; rclsid
0x1800241c2  call    cs:__imp_CoCreateInstance
0x1800241c9  nop     dword ptr [rax+rax+00h]
0x1800241ce  mov     ebx, eax
0x1800241d0  test    eax, eax
0x1800241d2  js      loc_1800243D2
0x1800241d8  mov     rcx, [rbp+57h+var_A0]
0x1800241dc  mov     rdx, r14
0x1800241df  mov     rax, [rcx]
0x1800241e2  mov     rax, [rax+28h]
0x1800241e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241eb  mov     ebx, eax
0x1800241ed  test    eax, eax
0x1800241ef  js      short loc_180024242
0x1800241f1  mov     rcx, [rbp+57h+var_A0]
0x1800241f5  lea     r8, [rbp+57h+var_A8]
0x1800241f9  mov     [rbp+57h+var_A8], 0
0x180024201  lea     rdx, IID_IPropertyBag
0x180024208  mov     rax, [rcx]
0x18002420b  mov     rax, [rax]
0x18002420e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024213  mov     ebx, eax
0x180024215  test    eax, eax
0x180024217  js      short loc_180024242
0x180024219  mov     rdx, [rbp+57h+var_A8]
0x18002421d  lea     rcx, [rdi+18h]
0x180024221  mov     rax, [rcx]
0x180024224  xor     r8d, r8d
0x180024227  mov     rax, [rax+28h]
0x18002422b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024230  mov     rcx, [rbp+57h+var_A8]
0x180024234  mov     ebx, eax
0x180024236  mov     rax, [rcx]
0x180024239  mov     rax, [rax+10h]
0x18002423d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024242  mov     rcx, [rbp+57h+var_A0]
0x180024246  mov     rax, [rcx]
0x180024249  mov     rax, [rax+10h]
0x18002424d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024252  test    ebx, ebx
0x180024254  js      loc_1800243D2
0x18002425a  cmp     dword ptr [rdi+8], 1
0x18002425e  jnz     loc_1800243D2
0x180024264  mov     rax, [r14]
0x180024267  lea     r9, [rbp+57h+var_AC]
0x18002426b  mov     r8d, 4
0x180024271  mov     [rbp+57h+var_AC], 0
0x180024278  lea     rdx, [rbp+57h+var_B0]
0x18002427c  mov     [rbp+57h+var_B0], 0
0x180024283  mov     rcx, r14
0x180024286  mov     rax, [rax+18h]
0x18002428a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002428f  mov     ebx, eax
0x180024291  test    eax, eax
0x180024293  js      loc_1800243D2
0x180024299  cmp     [rbp+57h+var_AC], 4
0x18002429d  jz      loc_1800243B6
0x1800242a3  mov     ebx, 80040243h
0x1800242a8  jmp     loc_1800243D2
0x1800242ad  mov     rax, [r14]
0x1800242b0  lea     r9, [rbp+57h+var_AC]
0x1800242b4  mov     r8d, 4
0x1800242ba  mov     dword ptr [rbp+57h+var_A8], 0
0x1800242c1  lea     rdx, [rbp+57h+var_A8]
0x1800242c5  mov     rcx, r14
0x1800242c8  mov     rax, [rax+18h]
0x1800242cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242d1  mov     ebx, eax
0x1800242d3  test    eax, eax
0x1800242d5  js      loc_1800243D2
0x1800242db  mov     eax, [rbp+57h+var_AC]
0x1800242de  lea     rcx, [rbp+57h+var_90]; void *
0x1800242e2  sub     [rbp+57h+var_B0], eax
0x1800242e5  xor     edx, edx; Val
0x1800242e7  lea     r8d, [rdx+58h]; Size
0x1800242eb  call    memset_0
0x1800242f0  mov     rax, [r14]
0x1800242f3  lea     r9, [rbp+57h+var_AC]
0x1800242f7  mov     r8d, 58h ; 'X'
0x1800242fd  lea     rdx, [rbp+57h+var_90]
0x180024301  mov     rcx, r14
0x180024304  mov     rax, [rax+18h]
0x180024308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002430d  mov     ebx, eax
0x18002430f  test    eax, eax
0x180024311  js      loc_1800243D2
0x180024317  mov     eax, [rbp+57h+var_AC]
0x18002431a  mov     ecx, [rbp+57h+var_90.cbFormat]; cb
0x18002431d  sub     [rbp+57h+var_B0], eax
0x180024320  call    cs:__imp_CoTaskMemAlloc
0x180024327  nop     dword ptr [rax+rax+00h]
0x18002432c  mov     [rbp+57h+var_90.pbFormat], rax
0x180024330  mov     rdx, rax
0x180024333  test    rax, rax
0x180024336  jz      loc_1800243CD
0x18002433c  mov     rax, [r14]
0x18002433f  lea     r9, [rbp+57h+var_AC]
0x180024343  mov     r8d, [rbp+57h+var_90.cbFormat]
0x180024347  mov     rcx, r14
0x18002434a  mov     rax, [rax+18h]
0x18002434e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024353  mov     ebx, eax
0x180024355  test    eax, eax
0x180024357  js      short loc_1800243C2
0x180024359  mov     eax, [rbp+57h+var_AC]
0x18002435c  sub     [rbp+57h+var_B0], eax
0x18002435f  mov     rsi, [rdi+0A8h]
0x180024366  jmp     short loc_18002438A
0x180024368  mov     r15, [rsi+10h]
0x18002436c  mov     rsi, [rsi+8]
0x180024370  mov     rdx, r15; struct CBasePin *
0x180024373  call    ?GetPinHandle@CKsProxy@@QEAAPEAXPEAVCBasePin@@@Z; CKsProxy::GetPinHandle(CBasePin *)
0x180024378  test    rax, rax
0x18002437b  jnz     short loc_18002438A
0x18002437d  mov     rdx, r15; struct CBasePin *
0x180024380  call    ?GetPinFactoryId@CKsProxy@@QEAAKPEAVCBasePin@@@Z; CKsProxy::GetPinFactoryId(CBasePin *)
0x180024385  cmp     dword ptr [rbp+57h+var_A8], eax
0x180024388  jz      short loc_180024391
0x18002438a  test    rsi, rsi
0x18002438d  jnz     short loc_180024368
0x18002438f  jmp     short loc_1800243A9
0x180024391  lea     rcx, [r15+18h]
0x180024395  xor     edx, edx
0x180024397  mov     rax, [rcx]
0x18002439a  lea     r8, [rbp+57h+var_90]
0x18002439e  mov     rax, [rax+18h]
0x1800243a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243a7  mov     ebx, eax
0x1800243a9  lea     rcx, [rbp+57h+var_90]; struct _AMMediaType *
0x1800243ad  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800243b2  test    ebx, ebx
0x1800243b4  js      short loc_1800243D2
0x1800243b6  cmp     [rbp+57h+var_B0], 0
0x1800243ba  jnz     loc_1800242AD
0x1800243c0  jmp     short loc_1800243D2
0x1800243c2  lea     rcx, [rbp+57h+var_90]; struct _AMMediaType *
0x1800243c6  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800243cb  jmp     short loc_1800243D2
0x1800243cd  mov     ebx, 8007000Eh
0x1800243d2  mov     eax, ebx
0x1800243d4  mov     rcx, [rbp+57h+var_30]
0x1800243d8  xor     rcx, rsp; StackCookie
0x1800243db  call    __security_check_cookie
0x1800243e0  mov     rbx, [rsp+0E0h+arg_10]
0x1800243e8  add     rsp, 0C0h
0x1800243ef  pop     r15
0x1800243f1  pop     r14
0x1800243f3  pop     rdi
0x1800243f4  pop     rsi
0x1800243f5  pop     rbp
0x1800243f6  retn
```
