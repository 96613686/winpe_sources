# CKsOutputPin2::DA_PluginInputItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)

- ea: `0x18002e750`
- end: `0x18002e8c5`
- name: `?DA_PluginInputItem@CKsOutputPin2@@SAXW4ASYNC_ITEM_STATUS@@PEAU_ASYNC_ITEM@@@Z`
- size: `373`
- prototype: `void __fastcall(enum ASYNC_ITEM_STATUS, struct _ASYNC_ITEM *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18001f1c4`
- `0x18002e750`
- `0x18002e9dc`
- `0x180031d5c`
- `0x180031e14`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002e832`
- `KERNEL32!GetLastError` at `0x18002e832`
- `KERNEL32!CloseHandle` at `0x18002e897`
- `KERNEL32!CloseHandle` at `0x18002e897`
- `KERNEL32!LeaveCriticalSection` at `0x18002e882`
- `KERNEL32!LeaveCriticalSection` at `0x18002e882`
- `KERNEL32!EnterCriticalSection` at `0x18002e7df`
- `KERNEL32!EnterCriticalSection` at `0x18002e7df`
- `KERNEL32!GetOverlappedResult` at `0x18002e822`
- `KERNEL32!GetOverlappedResult` at `0x18002e822`

## string_xrefs

- `0x18002e78e`: `CKsOutputPin2::DA_PluginInputItem`

## pseudocode

```c
void __fastcall CKsOutputPin2::DA_PluginInputItem(enum ASYNC_ITEM_STATUS a1, struct _ASYNC_ITEM *a2)
{
  struct _KSSTREAM_SEGMENT_EX2 **context; // rbx
  __int64 v5; // rsi
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  struct _KSSTREAM_SEGMENT_EX2 *v7; // rcx
  void *event; // rcx
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp+8h] BYREF

  context = (struct _KSSTREAM_SEGMENT_EX2 **)a2->context;
  v5 = *((_QWORD *)*context + 10);
  NumberOfBytesTransferred = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
      "CKsOutputPin2::DA_PluginInputItem");
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 2) != 0 )
    McTemplateU0pi_EventWriteTransfer(
      &Microsoft_Windows_DirectShow_KernelSupport_Context,
      DeviceIo_Complete,
      *(_QWORD *)(*((_QWORD *)context[2] + 69) + 40LL),
      *(_QWORD *)(*((_QWORD *)context[2] + 69) + 8LL));
  v6 = (struct _RTL_CRITICAL_SECTION *)(v5 + 408);
  EnterCriticalSection(v6);
  (*(void (__fastcall **)(__int64))(*((_QWORD *)*context + 48) + 112LL))((__int64)*context + 384);
  if ( a1 == EVENT_SIGNALLED )
  {
    if ( GetOverlappedResult(
           *((HANDLE *)*context + 65),
           (LPOVERLAPPED)((char *)context[2] + 560),
           &NumberOfBytesTransferred,
           0) )
    {
      v7 = *context;
      if ( *(_DWORD *)(*((_QWORD *)*context + 10) + 40LL)
        && !*((_DWORD *)v7 + 214)
        && !*((_DWORD *)v7 + 215)
        && !*((_DWORD *)v7 + 235)
        && *((_QWORD *)v7 + 27) )
      {
        CKsOutputPin2::DA_QueueBuffersToPluginInput(v7, context[2], context[1]);
      }
    }
    else
    {
      GetLastError();
    }
  }
  LeaveCriticalSection(v6);
  event = a2->event;
  if ( event )
    CloseHandle(event);
  operator delete(a2->context);
  operator delete(a2);
}

```

## disassembly

```asm
0x18002e750  push    rbx
0x18002e752  push    rbp
0x18002e753  push    rsi
0x18002e754  push    rdi
0x18002e755  sub     rsp, 28h
0x18002e759  mov     rbx, [rdx+28h]
0x18002e75d  mov     rdi, rdx
0x18002e760  mov     ebp, ecx
0x18002e762  mov     rax, [rbx]
0x18002e765  mov     rsi, [rax+50h]
0x18002e769  mov     [rsp+48h+NumberOfBytesTransferred], 0
0x18002e771  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e778  lea     rax, WPP_GLOBAL_Control
0x18002e77f  cmp     rcx, rax
0x18002e782  jz      short loc_18002E7A6
0x18002e784  cmp     byte ptr [rcx+19h], 2
0x18002e788  jb      short loc_18002E7A6
0x18002e78a  mov     rcx, [rcx+10h]
0x18002e78e  lea     r9, aCksoutputpin2D_5; "CKsOutputPin2::DA_PluginInputItem"
0x18002e795  mov     edx, 23h ; '#'
0x18002e79a  lea     r8, WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids
0x18002e7a1  call    WPP_SF_s
0x18002e7a6  test    cs:Microsoft_Windows_DirectShow_KernelSupportEnableBits, 2
0x18002e7ad  jz      short loc_18002E7D5
0x18002e7af  mov     rax, [rbx+10h]
0x18002e7b3  lea     rdx, DeviceIo_Complete
0x18002e7ba  lea     rcx, Microsoft_Windows_DirectShow_KernelSupport_Context
0x18002e7c1  mov     r8, [rax+228h]
0x18002e7c8  mov     r9, [r8+8]
0x18002e7cc  mov     r8, [r8+28h]
0x18002e7d0  call    McTemplateU0pi_EventWriteTransfer
0x18002e7d5  add     rsi, 198h
0x18002e7dc  mov     rcx, rsi; lpCriticalSection
0x18002e7df  call    cs:__imp_EnterCriticalSection
0x18002e7e6  nop     dword ptr [rax+rax+00h]
0x18002e7eb  mov     rcx, [rbx]
0x18002e7ee  add     rcx, 180h
0x18002e7f5  mov     rax, [rcx]
0x18002e7f8  mov     rax, [rax+70h]
0x18002e7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e801  test    ebp, ebp
0x18002e803  jnz     short loc_18002E87F
0x18002e805  mov     rcx, [rbx]
0x18002e808  lea     r8, [rsp+48h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002e80d  mov     rdx, [rbx+10h]
0x18002e811  xor     r9d, r9d; bWait
0x18002e814  add     rdx, 230h; lpOverlapped
0x18002e81b  mov     rcx, [rcx+208h]; hFile
0x18002e822  call    cs:__imp_GetOverlappedResult
0x18002e829  nop     dword ptr [rax+rax+00h]
0x18002e82e  test    eax, eax
0x18002e830  jnz     short loc_18002E840
0x18002e832  call    cs:__imp_GetLastError
0x18002e839  nop     dword ptr [rax+rax+00h]
0x18002e83e  jmp     short loc_18002E87F
0x18002e840  mov     rcx, [rbx]; this
0x18002e843  mov     rax, [rcx+50h]
0x18002e847  cmp     dword ptr [rax+28h], 0
0x18002e84b  jz      short loc_18002E87F
0x18002e84d  cmp     dword ptr [rcx+358h], 0
0x18002e854  jnz     short loc_18002E87F
0x18002e856  cmp     dword ptr [rcx+35Ch], 0
0x18002e85d  jnz     short loc_18002E87F
0x18002e85f  cmp     dword ptr [rcx+3ACh], 0
0x18002e866  jnz     short loc_18002E87F
0x18002e868  cmp     qword ptr [rcx+0D8h], 0
0x18002e870  jz      short loc_18002E87F
0x18002e872  mov     r8, [rbx+8]; struct _KSSTREAM_SEGMENT_EX2 *
0x18002e876  mov     rdx, [rbx+10h]; struct _KSSTREAM_SEGMENT_EX2 *
0x18002e87a  call    ?DA_QueueBuffersToPluginInput@CKsOutputPin2@@QEAAJPEAU_KSSTREAM_SEGMENT_EX2@@0@Z; CKsOutputPin2::DA_QueueBuffersToPluginInput(_KSSTREAM_SEGMENT_EX2 *,_KSSTREAM_SEGMENT_EX2 *)
0x18002e87f  mov     rcx, rsi; lpCriticalSection
0x18002e882  call    cs:__imp_LeaveCriticalSection
0x18002e889  nop     dword ptr [rax+rax+00h]
0x18002e88e  mov     rcx, [rdi+18h]; hObject
0x18002e892  test    rcx, rcx
0x18002e895  jz      short loc_18002E8A3
0x18002e897  call    cs:__imp_CloseHandle
0x18002e89e  nop     dword ptr [rax+rax+00h]
0x18002e8a3  mov     rcx, [rdi+28h]; void *
0x18002e8a7  xor     edx, edx; unsigned __int64
0x18002e8a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e8ae  mov     edx, 30h ; '0'; unsigned __int64
0x18002e8b3  mov     rcx, rdi; void *
0x18002e8b6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e8bb  add     rsp, 28h
0x18002e8bf  pop     rdi
0x18002e8c0  pop     rsi
0x18002e8c1  pop     rbp
0x18002e8c2  pop     rbx
0x18002e8c3  retn
```
