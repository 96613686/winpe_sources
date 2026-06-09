# CKsOutputPin2::InitializeAsyncThread(void)

- ea: `0x1001dfb0`
- end: `0x1001e1f2`
- name: `?InitializeAsyncThread@CKsOutputPin2@@UAEJXZ`
- size: `578`
- prototype: `unsigned int __thiscall(CKsOutputPin2 *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x10014a8b`
- `0x1001dfb0`
- `0x1002b9b9`
- `0x1002bd71`
- `0x1003a6fd`
- `0x1003af9d`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1001e049`
- `KERNEL32!CreateEventW` at `0x1001e05b`
- `KERNEL32!CreateEventW` at `0x1001e06d`
- `KERNEL32!CreateEventW` at `0x1001e07f`
- `KERNEL32!CreateEventW` at `0x1001e049`
- `KERNEL32!CreateEventW` at `0x1001e05b`
- `KERNEL32!CreateEventW` at `0x1001e06d`
- `KERNEL32!CreateEventW` at `0x1001e07f`
- `KERNEL32!CloseHandle` at `0x1001e196`
- `KERNEL32!CloseHandle` at `0x1001e1ad`
- `KERNEL32!CloseHandle` at `0x1001e1c4`
- `KERNEL32!CloseHandle` at `0x1001e1db`
- `KERNEL32!CloseHandle` at `0x1001e196`
- `KERNEL32!CloseHandle` at `0x1001e1ad`
- `KERNEL32!CloseHandle` at `0x1001e1c4`
- `KERNEL32!CloseHandle` at `0x1001e1db`

## pseudocode

```c
unsigned int __thiscall CKsOutputPin2::InitializeAsyncThread(CKsOutputPin2 *this)
{
  signed int v1; // edi
  CAsyncItemHandler *v3; // eax
  unsigned int v4; // ecx
  CAsyncItemHandler *v5; // eax
  unsigned int result; // eax
  _DWORD *v7; // edi
  _DWORD *v8; // ebx
  HANDLE EventW; // eax
  unsigned int v10; // ecx
  CAsyncItemHandler *v11; // ecx
  void *v12; // eax
  unsigned int v13; // [esp-4h] [ebp-1Ch]
  CAsyncItemHandler *v14; // [esp+0h] [ebp-18h]
  CAsyncItemHandler *v15; // [esp+0h] [ebp-18h]
  CAsyncItemHandler *v16; // [esp+0h] [ebp-18h]
  struct _ASYNC_ITEM *v17; // [esp+4h] [ebp-14h]
  struct _ASYNC_ITEM *v18; // [esp+4h] [ebp-14h]
  struct _ASYNC_ITEM *v19; // [esp+4h] [ebp-14h]
  unsigned int v20; // [esp+10h] [ebp-8h] BYREF
  int v21; // [esp+14h] [ebp-4h]

  v1 = 0;
  v21 = 0;
  v20 = 0;
  v3 = (CAsyncItemHandler *)operator new(0x23Cu);
  v4 = v13;
  if ( v3 )
  {
    v5 = CAsyncItemHandler::CAsyncItemHandler(v3, &v20);
    v1 = v20;
  }
  else
  {
    v5 = 0;
  }
  *((_DWORD *)this + 166) = v5;
  if ( v1 )
  {
    if ( v5 )
      CAsyncItemHandler::`scalar deleting destructor'(v5, v4);
    result = (unsigned __int16)v1 | 0x80070000;
    *((_DWORD *)this + 166) = 0;
    if ( v1 <= 0 )
      return v1;
  }
  else
  {
    v7 = operator new(0x18u);
    v8 = operator new(0x18u);
    v20 = (unsigned int)operator new(0x18u);
    *((_DWORD *)this + 161) = CreateEventW(0, 0, 0, 0);
    *((_DWORD *)this + 188) = CreateEventW(0, 0, 0, 0);
    *((_DWORD *)this + 162) = CreateEventW(0, 0, 0, 0);
    EventW = CreateEventW(0, 0, 0, 0);
    *((_DWORD *)this + 163) = EventW;
    if ( *((_DWORD *)this + 166)
      && v7
      && v8
      && *((_DWORD *)this + 161)
      && *((_DWORD *)this + 188)
      && *((_DWORD *)this + 162)
      && EventW )
    {
      v10 = v20;
      v8[1] = 0;
      *v8 = 0;
      *((_BYTE *)v8 + 8) = 0;
      v8[3] = *((_DWORD *)this + 162);
      v8[4] = CKsOutputPin::SynchronizeFlushRoutine;
      v8[5] = this;
      *(_DWORD *)(v10 + 4) = 0;
      *(_DWORD *)v10 = 0;
      *(_BYTE *)(v10 + 8) = 0;
      *(_DWORD *)(v10 + 12) = *((_DWORD *)this + 188);
      *(_DWORD *)(v10 + 16) = CKsOutputPin2::DeviceQueueItem;
      *(_DWORD *)(v10 + 20) = this;
      v7[1] = 0;
      *v7 = 0;
      *((_BYTE *)v7 + 8) = 0;
      v7[3] = *((_DWORD *)this + 161);
      v7[4] = CKsOutputPin::MarshalRoutine;
      v7[5] = this;
      CAsyncItemHandler::QueueAsyncItem(v14, v17);
      CAsyncItemHandler::QueueAsyncItem(v15, v18);
      CAsyncItemHandler::QueueAsyncItem(v16, v19);
    }
    else
    {
      v21 = -2147024882;
      operator delete(v7, 0x18u);
      operator delete(v8, 0x18u);
      v11 = (CAsyncItemHandler *)*((_DWORD *)this + 166);
      if ( v11 )
        CAsyncItemHandler::`scalar deleting destructor'(v11, *((_DWORD *)this + 166));
      v12 = (void *)*((_DWORD *)this + 161);
      *((_DWORD *)this + 166) = 0;
      if ( v12 )
      {
        CloseHandle(v12);
        *((_DWORD *)this + 161) = 0;
      }
      if ( *((_DWORD *)this + 188) )
      {
        CloseHandle(*((HANDLE *)this + 188));
        *((_DWORD *)this + 188) = 0;
      }
      if ( *((_DWORD *)this + 162) )
      {
        CloseHandle(*((HANDLE *)this + 162));
        *((_DWORD *)this + 162) = 0;
      }
      if ( *((_DWORD *)this + 163) )
      {
        CloseHandle(*((HANDLE *)this + 163));
        *((_DWORD *)this + 163) = 0;
      }
    }
    return v21;
  }
  return result;
}

```

## disassembly

```asm
0x1001dfb0  mov     edi, edi
0x1001dfb2  push    ebp
0x1001dfb3  mov     ebp, esp
0x1001dfb5  and     esp, 0FFFFFFF8h
0x1001dfb8  sub     esp, 0Ch
0x1001dfbb  push    ebx
0x1001dfbc  push    esi; struct _ASYNC_ITEM *
0x1001dfbd  push    edi; this
0x1001dfbe  xor     edi, edi
0x1001dfc0  mov     [esp+18h+var_4], 0
0x1001dfc8  push    23Ch; Size
0x1001dfcd  mov     esi, ecx
0x1001dfcf  mov     [esp+1Ch+var_8], edi
0x1001dfd3  call    ??2@YAPAXI@Z; operator new(uint)
0x1001dfd8  pop     ecx
0x1001dfd9  test    eax, eax
0x1001dfdb  jz      short loc_1001DFEF
0x1001dfdd  lea     ecx, [esp+18h+var_8]
0x1001dfe1  push    ecx; unsigned int *
0x1001dfe2  mov     ecx, eax; this
0x1001dfe4  call    ??0CAsyncItemHandler@@QAE@PAK@Z; CAsyncItemHandler::CAsyncItemHandler(ulong *)
0x1001dfe9  mov     edi, [esp+18h+var_8]
0x1001dfed  jmp     short loc_1001DFF1
0x1001dfef  xor     eax, eax
0x1001dff1  mov     [esi+298h], eax
0x1001dff7  test    edi, edi
0x1001dff9  jz      short loc_1001E023
0x1001dffb  test    eax, eax
0x1001dffd  jz      short loc_1001E007
0x1001dfff  push    ecx; unsigned int
0x1001e000  mov     ecx, eax; this
0x1001e002  call    ??_GCAsyncItemHandler@@QAEPAXI@Z; CAsyncItemHandler::`scalar deleting destructor'(uint)
0x1001e007  movzx   eax, di
0x1001e00a  or      eax, 80070000h
0x1001e00f  mov     dword ptr [esi+298h], 0
0x1001e019  test    edi, edi
0x1001e01b  cmovle  eax, edi
0x1001e01e  jmp     loc_1001E1EB
0x1001e023  push    18h; Size
0x1001e025  call    ??2@YAPAXI@Z; operator new(uint)
0x1001e02a  pop     ecx
0x1001e02b  push    18h; Size
0x1001e02d  mov     edi, eax
0x1001e02f  call    ??2@YAPAXI@Z; operator new(uint)
0x1001e034  pop     ecx
0x1001e035  push    18h; Size
0x1001e037  mov     ebx, eax
0x1001e039  call    ??2@YAPAXI@Z; operator new(uint)
0x1001e03e  pop     ecx
0x1001e03f  mov     [esp+18h+var_8], eax
0x1001e043  xor     eax, eax
0x1001e045  push    eax; lpName
0x1001e046  push    eax; bInitialState
0x1001e047  push    eax; bManualReset
0x1001e048  push    eax; lpEventAttributes
0x1001e049  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1001e04f  mov     [esi+284h], eax
0x1001e055  xor     eax, eax
0x1001e057  push    eax; lpName
0x1001e058  push    eax; bInitialState
0x1001e059  push    eax; bManualReset
0x1001e05a  push    eax; lpEventAttributes
0x1001e05b  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1001e061  mov     [esi+2F0h], eax
0x1001e067  xor     eax, eax
0x1001e069  push    eax; lpName
0x1001e06a  push    eax; bInitialState
0x1001e06b  push    eax; bManualReset
0x1001e06c  push    eax; lpEventAttributes
0x1001e06d  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1001e073  mov     [esi+288h], eax
0x1001e079  xor     eax, eax
0x1001e07b  push    eax; lpName
0x1001e07c  push    eax; bInitialState
0x1001e07d  push    eax; bManualReset
0x1001e07e  push    eax; lpEventAttributes
0x1001e07f  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1001e085  xor     edx, edx
0x1001e087  mov     [esi+28Ch], eax
0x1001e08d  cmp     [esi+298h], edx
0x1001e093  jz      loc_1001E158
0x1001e099  test    edi, edi
0x1001e09b  jz      loc_1001E158
0x1001e0a1  test    ebx, ebx
0x1001e0a3  jz      loc_1001E158
0x1001e0a9  cmp     [esi+284h], edx
0x1001e0af  jz      loc_1001E158
0x1001e0b5  cmp     [esi+2F0h], edx
0x1001e0bb  jz      loc_1001E158
0x1001e0c1  cmp     [esi+288h], edx
0x1001e0c7  jz      loc_1001E158
0x1001e0cd  test    eax, eax
0x1001e0cf  jz      loc_1001E158
0x1001e0d5  mov     ecx, [esp+18h+var_8]
0x1001e0d9  mov     [ebx+4], edx
0x1001e0dc  mov     [ebx], edx
0x1001e0de  mov     [ebx+8], dl
0x1001e0e1  mov     eax, [esi+288h]
0x1001e0e7  mov     [ebx+0Ch], eax
0x1001e0ea  mov     dword ptr [ebx+10h], offset ?SynchronizeFlushRoutine@CKsOutputPin@@SGXW4ASYNC_ITEM_STATUS@@PAU_ASYNC_ITEM@@@Z; CKsOutputPin::SynchronizeFlushRoutine(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x1001e0f1  mov     [ebx+14h], esi
0x1001e0f4  mov     [ecx+4], edx
0x1001e0f7  mov     [ecx], edx
0x1001e0f9  mov     [ecx+8], dl
0x1001e0fc  mov     eax, [esi+2F0h]
0x1001e102  mov     [ecx+0Ch], eax
0x1001e105  mov     dword ptr [ecx+10h], offset ?DeviceQueueItem@CKsOutputPin2@@SGXW4ASYNC_ITEM_STATUS@@PAU_ASYNC_ITEM@@@Z; CKsOutputPin2::DeviceQueueItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x1001e10c  mov     [ecx+14h], esi
0x1001e10f  mov     [edi+4], edx
0x1001e112  mov     [edi], edx
0x1001e114  mov     [edi+8], dl
0x1001e117  mov     edx, ebx
0x1001e119  mov     eax, [esi+284h]
0x1001e11f  mov     [edi+0Ch], eax
0x1001e122  mov     dword ptr [edi+10h], offset ?MarshalRoutine@CKsOutputPin@@SGXW4ASYNC_ITEM_STATUS@@PAU_ASYNC_ITEM@@@Z; CKsOutputPin::MarshalRoutine(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x1001e129  mov     [edi+14h], esi
0x1001e12c  mov     ecx, [esi+298h]
0x1001e132  call    ?QueueAsyncItem@CAsyncItemHandler@@QAGKPAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x1001e137  mov     ecx, [esi+298h]
0x1001e13d  mov     edx, edi
0x1001e13f  call    ?QueueAsyncItem@CAsyncItemHandler@@QAGKPAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x1001e144  mov     edx, [esp+18h+var_8]
0x1001e148  mov     ecx, [esi+298h]
0x1001e14e  call    ?QueueAsyncItem@CAsyncItemHandler@@QAGKPAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x1001e153  jmp     loc_1001E1E7
0x1001e158  push    18h; unsigned int
0x1001e15a  push    edi; Block
0x1001e15b  mov     [esp+20h+var_4], 8007000Eh
0x1001e163  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001e168  push    18h; unsigned int
0x1001e16a  push    ebx; Block
0x1001e16b  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001e170  mov     ecx, [esi+298h]; this
0x1001e176  add     esp, 10h
0x1001e179  test    ecx, ecx
0x1001e17b  jz      short loc_1001E183
0x1001e17d  push    ecx; unsigned int
0x1001e17e  call    ??_GCAsyncItemHandler@@QAEPAXI@Z; CAsyncItemHandler::`scalar deleting destructor'(uint)
0x1001e183  mov     eax, [esi+284h]
0x1001e189  xor     ebx, ebx
0x1001e18b  mov     [esi+298h], ebx
0x1001e191  test    eax, eax
0x1001e193  jz      short loc_1001E1A2
0x1001e195  push    eax; hObject
0x1001e196  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1001e19c  mov     [esi+284h], ebx
0x1001e1a2  mov     eax, [esi+2F0h]
0x1001e1a8  test    eax, eax
0x1001e1aa  jz      short loc_1001E1B9
0x1001e1ac  push    eax; hObject
0x1001e1ad  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1001e1b3  mov     [esi+2F0h], ebx
0x1001e1b9  mov     eax, [esi+288h]
0x1001e1bf  test    eax, eax
0x1001e1c1  jz      short loc_1001E1D0
0x1001e1c3  push    eax; hObject
0x1001e1c4  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1001e1ca  mov     [esi+288h], ebx
0x1001e1d0  mov     ecx, [esi+28Ch]
0x1001e1d6  test    ecx, ecx
0x1001e1d8  jz      short loc_1001E1E7
0x1001e1da  push    ecx; hObject
0x1001e1db  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1001e1e1  mov     [esi+28Ch], ebx
0x1001e1e7  mov     eax, [esp+18h+var_4]
0x1001e1eb  pop     edi
0x1001e1ec  pop     esi
0x1001e1ed  pop     ebx
0x1001e1ee  mov     esp, ebp
0x1001e1f0  pop     ebp
0x1001e1f1  retn
```
