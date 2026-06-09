# CMSMQMessage::~CMSMQMessage(void)

- ea: `0x180013630`
- end: `0x1800137aa`
- name: `??1CMSMQMessage@@UEAA@XZ`
- size: `378`
- prototype: `void __fastcall(CMSMQMessage *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ab58`
- `0x18000af30`
- `0x18000b540`

## callees

- `0x18000178c`
- `0x1800033ec`
- `0x180003848`
- `0x180013568`
- `0x180013590`
- `0x1800135d0`
- `0x180013600`
- `0x180013630`
- `0x180014658`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001378c`
- `KERNEL32!DeleteCriticalSection` at `0x18001378c`
- `KERNEL32!GlobalFree` at `0x18001365c`
- `KERNEL32!GlobalFree` at `0x18001365c`
- `mqrt!MQFreeSecurityContext` at `0x180013679`
- `mqrt!MQFreeSecurityContext` at `0x180013679`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMSMQMessage::~CMSMQMessage(CMSMQMessage *this)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( *((_DWORD *)this + 2591) != -1 )
    FreeReceiveBodyBuffer((char *)this + 10416);
  v2 = (void *)*((_QWORD *)this + 30);
  if ( v2 )
  {
    GlobalFree(v2);
    *((_QWORD *)this + 30) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 333);
  if ( v3 )
    MQFreeSecurityContext(v3);
  operator delete(*((void **)this + 3120));
  operator delete(*((void **)this + 3121));
  CBaseStaticBufferGrowing<unsigned char>::~CBaseStaticBufferGrowing<unsigned char>((char *)this + 20840);
  CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>((char *)this + 12624);
  CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>((char *)this + 8288);
  CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>((char *)this + 6208);
  CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>((char *)this + 5920);
  CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>((char *)this + 5632);
  CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>((char *)this + 5344);
  CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>((char *)this + 4504);
  CBaseStaticBufferGrowing<unsigned char>::~CBaseStaticBufferGrowing<unsigned char>((char *)this + 4344);
  CBaseStaticBufferGrowing<unsigned char>::~CBaseStaticBufferGrowing<unsigned char>((char *)this + 4064);
  CFakeGITInterface::~CFakeGITInterface((CMSMQMessage *)((char *)this + 4032));
  CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>((char *)this + 3744);
  CBaseStaticBufferGrowing<unsigned char>::~CBaseStaticBufferGrowing<unsigned char>((char *)this + 2680);
  CBaseStaticBufferGrowing<unsigned char>::~CBaseStaticBufferGrowing<unsigned char>((char *)this + 568);
  CBaseStaticBufferGrowing<unsigned char>::~CBaseStaticBufferGrowing<unsigned char>((char *)this + 408);
  CFakeGITInterface::~CFakeGITInterface((CMSMQMessage *)((char *)this + 320));
  CFakeGITInterface::~CFakeGITInterface((CMSMQMessage *)((char *)this + 288));
  CGITInterface::~CGITInterface((CMSMQMessage *)((char *)this + 256));
  CGITInterface::~CGITInterface((CMSMQMessage *)((char *)this + 168));
  CGITInterface::~CGITInterface((CMSMQMessage *)((char *)this + 136));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  R<IADs>::~R<IADs>((char *)this + 72);
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((CMSMQMessage *)((char *)this + 24));
}

```

## disassembly

```asm
0x180013630  push    rbx
0x180013632  sub     rsp, 20h
0x180013636  mov     rbx, rcx
0x180013639  mov     edx, [rcx+287Ch]
0x18001363f  cmp     edx, 0FFFFFFFFh
0x180013642  jz      short loc_180013650
0x180013644  add     rcx, 28B0h
0x18001364b  call    FreeReceiveBodyBuffer
0x180013650  mov     rcx, [rbx+0F0h]; hMem
0x180013657  test    rcx, rcx
0x18001365a  jz      short loc_18001366D
0x18001365c  call    cs:__imp_GlobalFree
0x180013662  mov     qword ptr [rbx+0F0h], 0
0x18001366d  mov     rcx, [rbx+0A68h]; hSecurityContext
0x180013674  test    rcx, rcx
0x180013677  jz      short loc_18001367F
0x180013679  call    cs:__imp_MQFreeSecurityContext
0x18001367f  mov     rcx, [rbx+6180h]; Block
0x180013686  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001368b  mov     rcx, [rbx+6188h]; Block
0x180013692  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013697  lea     rcx, [rbx+5168h]
0x18001369e  call    ??1?$CBaseStaticBufferGrowing@E@@UEAA@XZ; CBaseStaticBufferGrowing<uchar>::~CBaseStaticBufferGrowing<uchar>(void)
0x1800136a3  lea     rcx, [rbx+3150h]
0x1800136aa  call    ??1?$CBaseStaticBufferGrowing@_W@@UEAA@XZ; CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>(void)
0x1800136af  lea     rcx, [rbx+2060h]
0x1800136b6  call    ??1?$CBaseStaticBufferGrowing@_W@@UEAA@XZ; CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>(void)
0x1800136bb  lea     rcx, [rbx+1840h]
0x1800136c2  call    ??1?$CBaseStaticBufferGrowing@_W@@UEAA@XZ; CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>(void)
0x1800136c7  lea     rcx, [rbx+1720h]
0x1800136ce  call    ??1?$CBaseStaticBufferGrowing@_W@@UEAA@XZ; CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>(void)
0x1800136d3  lea     rcx, [rbx+1600h]
0x1800136da  call    ??1?$CBaseStaticBufferGrowing@_W@@UEAA@XZ; CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>(void)
0x1800136df  lea     rcx, [rbx+14E0h]
0x1800136e6  call    ??1?$CBaseStaticBufferGrowing@_W@@UEAA@XZ; CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>(void)
0x1800136eb  lea     rcx, [rbx+1198h]
0x1800136f2  call    ??1?$CBaseStaticBufferGrowing@_W@@UEAA@XZ; CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>(void)
0x1800136f7  lea     rcx, [rbx+10F8h]
0x1800136fe  call    ??1?$CBaseStaticBufferGrowing@E@@UEAA@XZ; CBaseStaticBufferGrowing<uchar>::~CBaseStaticBufferGrowing<uchar>(void)
0x180013703  lea     rcx, [rbx+0FE0h]
0x18001370a  call    ??1?$CBaseStaticBufferGrowing@E@@UEAA@XZ; CBaseStaticBufferGrowing<uchar>::~CBaseStaticBufferGrowing<uchar>(void)
0x18001370f  lea     rcx, [rbx+0FC0h]; this
0x180013716  call    ??1CFakeGITInterface@@UEAA@XZ; CFakeGITInterface::~CFakeGITInterface(void)
0x18001371b  lea     rcx, [rbx+0EA0h]
0x180013722  call    ??1?$CBaseStaticBufferGrowing@_W@@UEAA@XZ; CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>(void)
0x180013727  lea     rcx, [rbx+0A78h]
0x18001372e  call    ??1?$CBaseStaticBufferGrowing@E@@UEAA@XZ; CBaseStaticBufferGrowing<uchar>::~CBaseStaticBufferGrowing<uchar>(void)
0x180013733  lea     rcx, [rbx+238h]
0x18001373a  call    ??1?$CBaseStaticBufferGrowing@E@@UEAA@XZ; CBaseStaticBufferGrowing<uchar>::~CBaseStaticBufferGrowing<uchar>(void)
0x18001373f  lea     rcx, [rbx+198h]
0x180013746  call    ??1?$CBaseStaticBufferGrowing@E@@UEAA@XZ; CBaseStaticBufferGrowing<uchar>::~CBaseStaticBufferGrowing<uchar>(void)
0x18001374b  lea     rcx, [rbx+140h]; this
0x180013752  call    ??1CFakeGITInterface@@UEAA@XZ; CFakeGITInterface::~CFakeGITInterface(void)
0x180013757  lea     rcx, [rbx+120h]; this
0x18001375e  call    ??1CFakeGITInterface@@UEAA@XZ; CFakeGITInterface::~CFakeGITInterface(void)
0x180013763  lea     rcx, [rbx+100h]; this
0x18001376a  call    ??1CGITInterface@@UEAA@XZ; CGITInterface::~CGITInterface(void)
0x18001376f  lea     rcx, [rbx+0A8h]; this
0x180013776  call    ??1CGITInterface@@UEAA@XZ; CGITInterface::~CGITInterface(void)
0x18001377b  lea     rcx, [rbx+88h]; this
0x180013782  call    ??1CGITInterface@@UEAA@XZ; CGITInterface::~CGITInterface(void)
0x180013787  nop
0x180013788  lea     rcx, [rbx+50h]; lpCriticalSection
0x18001378c  call    cs:__imp_DeleteCriticalSection
0x180013792  nop
0x180013793  lea     rcx, [rbx+48h]
0x180013797  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x18001379c  lea     rcx, [rbx+18h]; this
0x1800137a0  add     rsp, 20h
0x1800137a4  pop     rbx
0x1800137a5  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
