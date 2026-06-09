# CKsOutputPin::InitializeAsyncThread(void)

- ea: `0x10018450`
- end: `0x10018623`
- name: `?InitializeAsyncThread@CKsOutputPin@@UAEJXZ`
- size: `467`
- prototype: `unsigned int __thiscall(CKsOutputPin *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x10014a8b`
- `0x10018450`
- `0x1002b9b9`
- `0x1002bd71`
- `0x1003a6fd`
- `0x1003af9d`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x100184f8`
- `KERNEL32!CreateEventW` at `0x1001850a`
- `KERNEL32!CreateEventW` at `0x1001851c`
- `KERNEL32!CreateEventW` at `0x100184f8`
- `KERNEL32!CreateEventW` at `0x1001850a`
- `KERNEL32!CreateEventW` at `0x1001851c`
- `KERNEL32!CloseHandle` at `0x100185de`
- `KERNEL32!CloseHandle` at `0x100185f5`
- `KERNEL32!CloseHandle` at `0x1001860c`
- `KERNEL32!CloseHandle` at `0x100185de`
- `KERNEL32!CloseHandle` at `0x100185f5`
- `KERNEL32!CloseHandle` at `0x1001860c`

## pseudocode

```c
unsigned int __thiscall CKsOutputPin::InitializeAsyncThread(CKsOutputPin *this)
{
  _DWORD *v2; // edi
  _DWORD *v3; // ebx
  CAsyncItemHandler *v4; // eax
  unsigned int v5; // ecx
  CAsyncItemHandler *v6; // eax
  bool v7; // zf
  signed int v8; // ecx
  unsigned int result; // eax
  HANDLE EventW; // eax
  CAsyncItemHandler *m_pAsyncItemHandler; // ecx
  void *m_hMarshalEvent; // eax
  size_t Size; // [esp+0h] [ebp-1Ch]
  CAsyncItemHandler *v14; // [esp+4h] [ebp-18h]
  CAsyncItemHandler *v15; // [esp+4h] [ebp-18h]
  struct _ASYNC_ITEM *v16; // [esp+8h] [ebp-14h]
  struct _ASYNC_ITEM *v17; // [esp+8h] [ebp-14h]
  unsigned int v18; // [esp+14h] [ebp-8h] BYREF
  int v19; // [esp+18h] [ebp-4h]

  v19 = 0;
  v2 = operator new(0x18u);
  v3 = operator new(0x18u);
  v18 = 0;
  v4 = (CAsyncItemHandler *)operator new(0x23Cu);
  v5 = Size;
  if ( v4 )
    v6 = CAsyncItemHandler::CAsyncItemHandler(v4, &v18);
  else
    v6 = 0;
  v7 = v18 == 0;
  this->m_pAsyncItemHandler = v6;
  if ( v7 )
  {
    this->m_hMarshalEvent = CreateEventW(0, 0, 0, 0);
    this->m_hFlushEvent = CreateEventW(0, 0, 0, 0);
    EventW = CreateEventW(0, 0, 0, 0);
    this->m_hFlushCompleteEvent = EventW;
    if ( this->m_pAsyncItemHandler && v2 && v3 && this->m_hMarshalEvent && this->m_hFlushEvent && EventW )
    {
      v3[1] = 0;
      *v3 = 0;
      *((_BYTE *)v3 + 8) = 0;
      v3[3] = this->m_hFlushEvent;
      v3[4] = CKsOutputPin::SynchronizeFlushRoutine;
      v3[5] = this;
      v2[1] = 0;
      *v2 = 0;
      *((_BYTE *)v2 + 8) = 0;
      v2[3] = this->m_hMarshalEvent;
      v2[4] = CKsOutputPin::MarshalRoutine;
      v2[5] = this;
      CAsyncItemHandler::QueueAsyncItem(v14, v16);
      CAsyncItemHandler::QueueAsyncItem(v15, v17);
    }
    else
    {
      v19 = -2147024882;
      operator delete(v2, 0x18u);
      operator delete(v3, 0x18u);
      m_pAsyncItemHandler = this->m_pAsyncItemHandler;
      if ( m_pAsyncItemHandler )
        CAsyncItemHandler::`scalar deleting destructor'(m_pAsyncItemHandler, (unsigned int)this->m_pAsyncItemHandler);
      m_hMarshalEvent = this->m_hMarshalEvent;
      this->m_pAsyncItemHandler = 0;
      if ( m_hMarshalEvent )
      {
        CloseHandle(m_hMarshalEvent);
        this->m_hMarshalEvent = 0;
      }
      if ( this->m_hFlushEvent )
      {
        CloseHandle(this->m_hFlushEvent);
        this->m_hFlushEvent = 0;
      }
      if ( this->m_hFlushCompleteEvent )
      {
        CloseHandle(this->m_hFlushCompleteEvent);
        this->m_hFlushCompleteEvent = 0;
      }
    }
    return v19;
  }
  else
  {
    if ( v6 )
      CAsyncItemHandler::`scalar deleting destructor'(v6, v5);
    operator delete(v2, 0x18u);
    operator delete(v3, 0x18u);
    v8 = v18;
    result = (unsigned __int16)v18 | 0x80070000;
    this->m_pAsyncItemHandler = 0;
    if ( v8 <= 0 )
      return v8;
  }
  return result;
}

```

## disassembly

```asm
0x10018450  mov     edi, edi
0x10018452  push    ebp
0x10018453  mov     ebp, esp
0x10018455  and     esp, 0FFFFFFF8h
0x10018458  sub     esp, 0Ch
0x1001845b  push    ebx
0x1001845c  push    esi; struct _ASYNC_ITEM *
0x1001845d  push    edi; this
0x1001845e  push    18h; Size
0x10018460  mov     esi, ecx
0x10018462  mov     [esp+1Ch+var_4], 0
0x1001846a  call    ??2@YAPAXI@Z; operator new(uint)
0x1001846f  pop     ecx
0x10018470  push    18h; Size
0x10018472  mov     edi, eax
0x10018474  call    ??2@YAPAXI@Z; operator new(uint)
0x10018479  mov     ebx, eax
0x1001847b  mov     [esp+1Ch+var_8], 0
0x10018483  mov     [esp+1Ch+Size], 23Ch; Size
0x1001848a  call    ??2@YAPAXI@Z; operator new(uint)
0x1001848f  pop     ecx
0x10018490  test    eax, eax
0x10018492  jz      short loc_100184A2
0x10018494  lea     ecx, [esp+18h+var_8]
0x10018498  push    ecx; unsigned int *
0x10018499  mov     ecx, eax; this
0x1001849b  call    ??0CAsyncItemHandler@@QAE@PAK@Z; CAsyncItemHandler::CAsyncItemHandler(ulong *)
0x100184a0  jmp     short loc_100184A4
0x100184a2  xor     eax, eax
0x100184a4  cmp     [esp+18h+var_8], 0
0x100184a9  mov     [esi+298h], eax
0x100184af  jz      short loc_100184F0
0x100184b1  test    eax, eax
0x100184b3  jz      short loc_100184BD
0x100184b5  push    ecx; unsigned int
0x100184b6  mov     ecx, eax; this
0x100184b8  call    ??_GCAsyncItemHandler@@QAEPAXI@Z; CAsyncItemHandler::`scalar deleting destructor'(uint)
0x100184bd  push    18h; unsigned int
0x100184bf  push    edi; Block
0x100184c0  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100184c5  push    18h; unsigned int
0x100184c7  push    ebx; Block
0x100184c8  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100184cd  mov     ecx, [esp+28h+var_8]
0x100184d1  add     esp, 10h
0x100184d4  movzx   eax, cx
0x100184d7  or      eax, 80070000h
0x100184dc  mov     dword ptr [esi+298h], 0
0x100184e6  test    ecx, ecx
0x100184e8  cmovle  eax, ecx
0x100184eb  jmp     loc_1001861C
0x100184f0  push    0; lpName
0x100184f2  push    0; bInitialState
0x100184f4  push    0; bManualReset
0x100184f6  push    0; lpEventAttributes
0x100184f8  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x100184fe  mov     [esi+284h], eax
0x10018504  xor     eax, eax
0x10018506  push    eax; lpName
0x10018507  push    eax; bInitialState
0x10018508  push    eax; bManualReset
0x10018509  push    eax; lpEventAttributes
0x1001850a  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10018510  mov     [esi+288h], eax
0x10018516  xor     eax, eax
0x10018518  push    eax; lpName
0x10018519  push    eax; bInitialState
0x1001851a  push    eax; bManualReset
0x1001851b  push    eax; lpEventAttributes
0x1001851c  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10018522  xor     ecx, ecx
0x10018524  mov     [esi+28Ch], eax
0x1001852a  cmp     [esi+298h], ecx
0x10018530  jz      short loc_100185A0
0x10018532  test    edi, edi
0x10018534  jz      short loc_100185A0
0x10018536  test    ebx, ebx
0x10018538  jz      short loc_100185A0
0x1001853a  cmp     [esi+284h], ecx
0x10018540  jz      short loc_100185A0
0x10018542  cmp     [esi+288h], ecx
0x10018548  jz      short loc_100185A0
0x1001854a  test    eax, eax
0x1001854c  jz      short loc_100185A0
0x1001854e  mov     [ebx+4], ecx
0x10018551  mov     edx, ebx
0x10018553  mov     [ebx], ecx
0x10018555  mov     [ebx+8], cl
0x10018558  mov     eax, [esi+288h]
0x1001855e  mov     [ebx+0Ch], eax
0x10018561  mov     dword ptr [ebx+10h], offset ?SynchronizeFlushRoutine@CKsOutputPin@@SGXW4ASYNC_ITEM_STATUS@@PAU_ASYNC_ITEM@@@Z; CKsOutputPin::SynchronizeFlushRoutine(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x10018568  mov     [ebx+14h], esi
0x1001856b  mov     [edi+4], ecx
0x1001856e  mov     [edi], ecx
0x10018570  mov     [edi+8], cl
0x10018573  mov     eax, [esi+284h]
0x10018579  mov     [edi+0Ch], eax
0x1001857c  mov     dword ptr [edi+10h], offset ?MarshalRoutine@CKsOutputPin@@SGXW4ASYNC_ITEM_STATUS@@PAU_ASYNC_ITEM@@@Z; CKsOutputPin::MarshalRoutine(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x10018583  mov     [edi+14h], esi
0x10018586  mov     ecx, [esi+298h]
0x1001858c  call    ?QueueAsyncItem@CAsyncItemHandler@@QAGKPAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x10018591  mov     ecx, [esi+298h]
0x10018597  mov     edx, edi
0x10018599  call    ?QueueAsyncItem@CAsyncItemHandler@@QAGKPAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x1001859e  jmp     short loc_10018618
0x100185a0  push    18h; unsigned int
0x100185a2  push    edi; Block
0x100185a3  mov     [esp+20h+var_4], 8007000Eh
0x100185ab  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100185b0  push    18h; unsigned int
0x100185b2  push    ebx; Block
0x100185b3  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100185b8  mov     ecx, [esi+298h]; this
0x100185be  add     esp, 10h
0x100185c1  test    ecx, ecx
0x100185c3  jz      short loc_100185CB
0x100185c5  push    ecx; unsigned int
0x100185c6  call    ??_GCAsyncItemHandler@@QAEPAXI@Z; CAsyncItemHandler::`scalar deleting destructor'(uint)
0x100185cb  mov     eax, [esi+284h]
0x100185d1  xor     ebx, ebx
0x100185d3  mov     [esi+298h], ebx
0x100185d9  test    eax, eax
0x100185db  jz      short loc_100185EA
0x100185dd  push    eax; hObject
0x100185de  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100185e4  mov     [esi+284h], ebx
0x100185ea  mov     eax, [esi+288h]
0x100185f0  test    eax, eax
0x100185f2  jz      short loc_10018601
0x100185f4  push    eax; hObject
0x100185f5  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100185fb  mov     [esi+288h], ebx
0x10018601  mov     ecx, [esi+28Ch]
0x10018607  test    ecx, ecx
0x10018609  jz      short loc_10018618
0x1001860b  push    ecx; hObject
0x1001860c  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10018612  mov     [esi+28Ch], ebx
0x10018618  mov     eax, [esp+18h+var_4]
0x1001861c  pop     edi
0x1001861d  pop     esi
0x1001861e  pop     ebx
0x1001861f  mov     esp, ebp
0x10018621  pop     ebp
0x10018622  retn
```
