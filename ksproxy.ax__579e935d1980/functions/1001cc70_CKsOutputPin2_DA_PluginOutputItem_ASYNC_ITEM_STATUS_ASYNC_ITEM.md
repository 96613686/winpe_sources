# CKsOutputPin2::DA_PluginOutputItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)

- ea: `0x1001cc70`
- end: `0x1001cd40`
- name: `?DA_PluginOutputItem@CKsOutputPin2@@SGXW4ASYNC_ITEM_STATUS@@PAU_ASYNC_ITEM@@@Z`
- size: `208`
- prototype: `static void __stdcall(enum ASYNC_ITEM_STATUS, struct _ASYNC_ITEM *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callees

- `0x1001a001`
- `0x1001cb15`
- `0x1001cc70`
- `0x1002be36`
- `0x1003af9d`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1001cd27`
- `KERNEL32!CloseHandle` at `0x1001cd27`
- `KERNEL32!LeaveCriticalSection` at `0x1001cd18`
- `KERNEL32!LeaveCriticalSection` at `0x1001cd18`
- `KERNEL32!EnterCriticalSection` at `0x1001ccbe`
- `KERNEL32!EnterCriticalSection` at `0x1001ccbe`

## string_xrefs

- `0x1001cc99`: `CKsOutputPin2::DA_PluginOutputItem`

## pseudocode

```c
void __stdcall CKsOutputPin2::DA_PluginOutputItem(enum ASYNC_ITEM_STATUS a1, struct _ASYNC_ITEM *Block)
{
  int *context; // edi
  int v3; // ebx
  struct _RTL_CRITICAL_SECTION *v4; // ebx
  _DWORD *v5; // ecx
  int v6; // eax

  context = (int *)Block->context;
  v3 = *(_DWORD *)(*context + 40);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_s(
      0x21u,
      &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (int)"CKsOutputPin2::DA_PluginOutputItem");
  if ( a1 == EVENT_SIGNALLED )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)(v3 + 244);
    EnterCriticalSection(v4);
    v5 = (_DWORD *)*context;
    if ( *(_DWORD *)(*(_DWORD *)(*context + 40) + 20) && !v5[144] && !v5[145] && !v5[160] && v5[38] )
      CKsOutputPin2::DA_QueueBuffersToPluginOutput((int)v5, context[1]);
    v6 = *(_DWORD *)(*context + 492);
    if ( v6 && *(_DWORD *)(v6 + 8) )
      CAsyncItemHandler::QueueAsyncItemList(*(_DWORD *)(*context + 664));
    LeaveCriticalSection(v4);
  }
  if ( Block->event )
    CloseHandle(Block->event);
  operator delete(Block, 0x18u);
}

```

## disassembly

```asm
0x1001cc70  mov     edi, edi
0x1001cc72  push    ebp
0x1001cc73  mov     ebp, esp
0x1001cc75  and     esp, 0FFFFFFF8h
0x1001cc78  push    ecx
0x1001cc79  push    ebx
0x1001cc7a  push    esi; struct _KSSTREAM_SEGMENT_EX2 *
0x1001cc7b  mov     esi, [ebp+Block]
0x1001cc7e  push    edi; this
0x1001cc7f  mov     edi, [esi+14h]
0x1001cc82  mov     eax, [edi]
0x1001cc84  mov     ebx, [eax+28h]
0x1001cc87  mov     eax, _WPP_GLOBAL_Control
0x1001cc8c  cmp     eax, offset _WPP_GLOBAL_Control
0x1001cc91  jz      short loc_1001CCB1
0x1001cc93  cmp     byte ptr [eax+19h], 2
0x1001cc97  jb      short loc_1001CCB1
0x1001cc99  push    offset aCksoutputpin2D_0; "CKsOutputPin2::DA_PluginOutputItem"
0x1001cc9e  push    dword ptr [eax+14h]
0x1001cca1  mov     edx, offset _WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids; MessageGuid
0x1001cca6  push    dword ptr [eax+10h]; LoggerHandle
0x1001cca9  push    21h ; '!'
0x1001ccab  pop     ecx; MessageNumber
0x1001ccac  call    _WPP_SF_s@20; WPP_SF_s(x,x,x,x,x)
0x1001ccb1  cmp     [ebp+arg_0], 0
0x1001ccb5  jnz     short loc_1001CD1E
0x1001ccb7  add     ebx, 0F4h
0x1001ccbd  push    ebx; lpCriticalSection
0x1001ccbe  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001ccc4  mov     ecx, [edi]
0x1001ccc6  xor     edx, edx
0x1001ccc8  mov     eax, [ecx+28h]
0x1001cccb  cmp     [eax+14h], edx
0x1001ccce  jz      short loc_1001CCF8
0x1001ccd0  cmp     [ecx+240h], edx
0x1001ccd6  jnz     short loc_1001CCF8
0x1001ccd8  cmp     [ecx+244h], edx
0x1001ccde  jnz     short loc_1001CCF8
0x1001cce0  cmp     [ecx+280h], edx
0x1001cce6  jnz     short loc_1001CCF8
0x1001cce8  cmp     [ecx+98h], edx
0x1001ccee  jz      short loc_1001CCF8
0x1001ccf0  mov     edx, [edi+4]
0x1001ccf3  call    ?DA_QueueBuffersToPluginOutput@CKsOutputPin2@@QAGJPAU_KSSTREAM_SEGMENT_EX2@@@Z; CKsOutputPin2::DA_QueueBuffersToPluginOutput(_KSSTREAM_SEGMENT_EX2 *)
0x1001ccf8  mov     ecx, [edi]
0x1001ccfa  lea     edx, [ecx+1ECh]
0x1001cd00  mov     eax, [edx]
0x1001cd02  test    eax, eax
0x1001cd04  jz      short loc_1001CD17
0x1001cd06  cmp     dword ptr [eax+8], 0
0x1001cd0a  jz      short loc_1001CD17
0x1001cd0c  mov     ecx, [ecx+298h]
0x1001cd12  call    ?QueueAsyncItemList@CAsyncItemHandler@@QAGKPAV?$CGenericList@U_ASYNC_ITEM@@@@@Z; CAsyncItemHandler::QueueAsyncItemList(CGenericList<_ASYNC_ITEM> *)
0x1001cd17  push    ebx; lpCriticalSection
0x1001cd18  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001cd1e  cmp     dword ptr [esi+0Ch], 0
0x1001cd22  jz      short loc_1001CD2D
0x1001cd24  push    dword ptr [esi+0Ch]; hObject
0x1001cd27  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1001cd2d  push    18h; unsigned int
0x1001cd2f  push    esi; Block
0x1001cd30  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001cd35  pop     ecx
0x1001cd36  pop     ecx
0x1001cd37  pop     edi
0x1001cd38  pop     esi
0x1001cd39  pop     ebx
0x1001cd3a  mov     esp, ebp
0x1001cd3c  pop     ebp
0x1001cd3d  retn    8
```
