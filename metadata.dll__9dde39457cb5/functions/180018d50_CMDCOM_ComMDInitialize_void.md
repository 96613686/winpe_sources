# CMDCOM::ComMDInitialize(void)

- ea: `0x180018d50`
- end: `0x180018ef1`
- name: `?ComMDInitialize@CMDCOM@@UEAAJXZ`
- size: `417`
- prototype: `__int64 __fastcall(struct IUnknown *this)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800089c8`
- `0x180015bf8`
- `0x180018d50`
- `0x18001f110`
- `0x18001fa58`
- `0x180027aec`
- `0x1800280e0`
- `0x180031010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180018e9f`
- `KERNEL32!LeaveCriticalSection` at `0x180018e9f`
- `KERNEL32!EnterCriticalSection` at `0x180018e7a`
- `KERNEL32!EnterCriticalSection` at `0x180018e7a`
- `IisRTL!RemoveWorkItem` at `0x180018e8f`
- `IisRTL!RemoveWorkItem` at `0x180018e8f`
- `IisRTL!IISInitializeCriticalSection` at `0x180018d96`
- `IisRTL!IISInitializeCriticalSection` at `0x180018d96`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDInitialize(struct IUnknown *this)
{
  int v1; // esi
  int inited; // ebx
  COConnectionPoint *v4; // rax
  COConnectionPoint *v5; // rax
  COConnectionPoint *v6; // rsi
  unsigned int v7; // edx
  COConnectionPoint *v8; // rax
  COConnectionPoint *v9; // rax
  unsigned int lpVtbl; // ecx

  v1 = 0;
  if ( !_InterlockedCompareExchange(&g_fOneTimeInitialized, 1, 0) )
  {
    inited = InitOneTimeGlobals();
    if ( inited < 0 )
      return (unsigned int)inited;
    *(struct IUnknownVtbl **)((char *)&this[6].lpVtbl + 4) = 0;
    HIDWORD(this[7].lpVtbl) = 120000;
    if ( (unsigned int)IISInitializeCriticalSection(&this[10]) )
    {
      LODWORD(this[9].lpVtbl) = 1;
      v4 = (COConnectionPoint *)operator new(0x40u);
      if ( v4 )
      {
        v5 = COConnectionPoint::COConnectionPoint(v4, this);
        v6 = v5;
        if ( v5 )
        {
          inited = COConnectionPoint::Init(v5, &IID_IMDCOMSINK_A);
          if ( inited < 0 )
            goto LABEL_22;
          inited = (**(__int64 (__fastcall ***)(COConnectionPoint *, GUID *, struct IUnknown *))v6)(
                     v6,
                     &IID_IConnectionPoint,
                     this + 4);
          if ( inited < 0 )
            goto LABEL_22;
          v8 = (COConnectionPoint *)operator new(0x40u);
          if ( v8 )
          {
            v9 = COConnectionPoint::COConnectionPoint(v8, this);
            v6 = v9;
            if ( v9 )
            {
              inited = COConnectionPoint::Init(v9, &IID_IMDCOMSINK_W);
              if ( inited >= 0 )
              {
                inited = (**(__int64 (__fastcall ***)(COConnectionPoint *, GUID *, struct IUnknown *))v6)(
                           v6,
                           &IID_IConnectionPoint,
                           this + 5);
                if ( inited >= 0 )
                {
                  v1 = 1;
                  if ( !HIDWORD(this[6].lpVtbl) )
                  {
                    HIDWORD(this[6].lpVtbl) = 1;
                    EnterCriticalSection((LPCRITICAL_SECTION)&this[10]);
                    lpVtbl = (unsigned int)this[7].lpVtbl;
                    this[8].lpVtbl = 0;
                    if ( lpVtbl )
                    {
                      RemoveWorkItem(lpVtbl);
                      LODWORD(this[7].lpVtbl) = 0;
                    }
                    LeaveCriticalSection((LPCRITICAL_SECTION)&this[10]);
                  }
                  goto LABEL_17;
                }
              }
LABEL_22:
              COConnectionPoint::`scalar deleting destructor'(v6, v7);
              return (unsigned int)inited;
            }
          }
        }
      }
    }
    return (unsigned int)-2147024882;
  }
LABEL_17:
  inited = InitWorker(0, 0, 0, 0, 0);
  if ( inited >= 0 )
  {
    if ( v1 )
      ((void (__fastcall *)(struct IUnknown *))this->lpVtbl[22].QueryInterface)(this);
    return 0;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180018d50  push    rbx
0x180018d52  push    rbp
0x180018d53  push    rsi
0x180018d54  push    rdi
0x180018d55  push    r15
0x180018d57  sub     rsp, 30h
0x180018d5b  xor     esi, esi
0x180018d5d  mov     rdi, rcx
0x180018d60  xor     eax, eax
0x180018d62  lea     r15d, [rsi+1]
0x180018d66  lock cmpxchg cs:?g_fOneTimeInitialized@@3JA, r15d; long g_fOneTimeInitialized
0x180018d6f  jnz     loc_180018EA5
0x180018d75  call    ?InitOneTimeGlobals@@YAJXZ; InitOneTimeGlobals(void)
0x180018d7a  mov     ebx, eax
0x180018d7c  test    eax, eax
0x180018d7e  js      loc_180018EDA
0x180018d84  lea     rbp, [rdi+50h]
0x180018d88  mov     [rdi+34h], rsi
0x180018d8c  mov     rcx, rbp
0x180018d8f  mov     dword ptr [rdi+3Ch], 1D4C0h
0x180018d96  call    cs:__imp_IISInitializeCriticalSection
0x180018d9c  test    eax, eax
0x180018d9e  jnz     short loc_180018DAA
0x180018da0  mov     ebx, 8007000Eh
0x180018da5  jmp     loc_180018EDA
0x180018daa  mov     ecx, 40h ; '@'; Size
0x180018daf  mov     [rdi+48h], r15d
0x180018db3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018db8  test    rax, rax
0x180018dbb  jz      short loc_180018DA0
0x180018dbd  mov     rdx, rdi; struct IUnknown *
0x180018dc0  mov     rcx, rax; this
0x180018dc3  call    ??0COConnectionPoint@@QEAA@PEAUIUnknown@@@Z; COConnectionPoint::COConnectionPoint(IUnknown *)
0x180018dc8  mov     rsi, rax
0x180018dcb  test    rax, rax
0x180018dce  jz      short loc_180018DA0
0x180018dd0  lea     rdx, IID_IMDCOMSINK_A; struct _GUID *
0x180018dd7  mov     rcx, rax; this
0x180018dda  call    ?Init@COConnectionPoint@@QEAAJAEBU_GUID@@@Z; COConnectionPoint::Init(_GUID const &)
0x180018ddf  mov     ebx, eax
0x180018de1  test    eax, eax
0x180018de3  js      loc_180018EE7
0x180018de9  mov     rdx, [rsi]
0x180018dec  lea     r8, [rdi+20h]
0x180018df0  mov     rcx, rsi
0x180018df3  mov     rax, [rdx]
0x180018df6  lea     rdx, IID_IConnectionPoint
0x180018dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e02  mov     ebx, eax
0x180018e04  test    eax, eax
0x180018e06  js      loc_180018EE7
0x180018e0c  mov     ecx, 40h ; '@'; Size
0x180018e11  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018e16  test    rax, rax
0x180018e19  jz      short loc_180018DA0
0x180018e1b  mov     rdx, rdi; struct IUnknown *
0x180018e1e  mov     rcx, rax; this
0x180018e21  call    ??0COConnectionPoint@@QEAA@PEAUIUnknown@@@Z; COConnectionPoint::COConnectionPoint(IUnknown *)
0x180018e26  mov     rsi, rax
0x180018e29  test    rax, rax
0x180018e2c  jz      loc_180018DA0
0x180018e32  lea     rdx, IID_IMDCOMSINK_W; struct _GUID *
0x180018e39  mov     rcx, rax; this
0x180018e3c  call    ?Init@COConnectionPoint@@QEAAJAEBU_GUID@@@Z; COConnectionPoint::Init(_GUID const &)
0x180018e41  mov     ebx, eax
0x180018e43  test    eax, eax
0x180018e45  js      loc_180018EE7
0x180018e4b  mov     rcx, [rsi]
0x180018e4e  lea     r8, [rdi+28h]
0x180018e52  lea     rdx, IID_IConnectionPoint
0x180018e59  mov     rax, [rcx]
0x180018e5c  mov     rcx, rsi
0x180018e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e64  mov     ebx, eax
0x180018e66  test    eax, eax
0x180018e68  js      short loc_180018EE7
0x180018e6a  cmp     dword ptr [rdi+34h], 0
0x180018e6e  mov     esi, r15d
0x180018e71  jnz     short loc_180018EA5
0x180018e73  mov     rcx, rbp; lpCriticalSection
0x180018e76  mov     [rdi+34h], r15d
0x180018e7a  call    cs:__imp_EnterCriticalSection
0x180018e80  mov     ecx, [rdi+38h]
0x180018e83  mov     qword ptr [rdi+40h], 0
0x180018e8b  test    ecx, ecx
0x180018e8d  jz      short loc_180018E9C
0x180018e8f  call    cs:__imp_?RemoveWorkItem@@YAHK@Z; RemoveWorkItem(ulong)
0x180018e95  mov     dword ptr [rdi+38h], 0
0x180018e9c  mov     rcx, rbp; lpCriticalSection
0x180018e9f  call    cs:__imp_LeaveCriticalSection
0x180018ea5  xor     r9d, r9d; char *
0x180018ea8  mov     [rsp+58h+var_38], 0; int
0x180018eb0  xor     r8d, r8d; char *
0x180018eb3  xor     edx, edx; char *
0x180018eb5  xor     ecx, ecx; int
0x180018eb7  call    ?InitWorker@@YAJHPEAD00H@Z; InitWorker(int,char *,char *,char *,int)
0x180018ebc  mov     ebx, eax
0x180018ebe  test    eax, eax
0x180018ec0  js      short loc_180018EDA
0x180018ec2  test    esi, esi
0x180018ec4  jz      short loc_180018ED8
0x180018ec6  mov     rax, [rdi]
0x180018ec9  mov     rcx, rdi
0x180018ecc  mov     rax, [rax+210h]
0x180018ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ed8  xor     ebx, ebx
0x180018eda  mov     eax, ebx
0x180018edc  add     rsp, 30h
0x180018ee0  pop     r15
0x180018ee2  pop     rdi
0x180018ee3  pop     rsi
0x180018ee4  pop     rbp
0x180018ee5  pop     rbx
0x180018ee6  retn
0x180018ee7  mov     rcx, rsi; this
0x180018eea  call    ??_GCOConnectionPoint@@QEAAPEAXI@Z; COConnectionPoint::`scalar deleting destructor'(uint)
0x180018eef  jmp     short loc_180018EDA
```
