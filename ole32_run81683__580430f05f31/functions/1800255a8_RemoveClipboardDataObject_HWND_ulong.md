# RemoveClipboardDataObject(HWND__ *,ulong)

- ea: `0x1800255a8`
- end: `0x180025706`
- name: `?RemoveClipboardDataObject@@YAJPEAUHWND__@@K@Z`
- size: `350`
- prototype: `HRESULT __fastcall(HWND__ *hClipWnd, unsigned int fFlags)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001933c`
- `0x1800254a0`

## callees

- `0x1800255a8`
- `0x18002570c`
- `0x1800323f0`
- `0x18008c3c0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025664`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025664`
- `USER32!SetWindowLongPtrW` at `0x180025600`
- `USER32!SetWindowLongPtrW` at `0x180025600`
- `USER32!GetPropW` at `0x1800255c7`
- `USER32!GetPropW` at `0x1800255da`
- `USER32!GetPropW` at `0x1800255ed`
- `USER32!GetPropW` at `0x1800255c7`
- `USER32!GetPropW` at `0x1800255da`
- `USER32!GetPropW` at `0x1800255ed`
- `USER32!IsClipboardFormatAvailable` at `0x1800256d3`
- `USER32!IsClipboardFormatAvailable` at `0x1800256d3`
- `USER32!RemovePropW` at `0x18002561b`
- `USER32!RemovePropW` at `0x18002562b`
- `USER32!RemovePropW` at `0x18002563b`
- `USER32!RemovePropW` at `0x18002561b`
- `USER32!RemovePropW` at `0x18002562b`
- `USER32!RemovePropW` at `0x18002563b`

## pseudocode

```c
__int64 __fastcall RemoveClipboardDataObject(HWND hClipWnd, char fFlags)
{
  unsigned int v3; // ebp
  HANDLE PropW; // rsi
  HANDLE v6; // rdi
  void *v7; // rax
  unsigned int dwAssignPID; // [rsp+58h] [rbp+10h] BYREF
  IDataObject *pData; // [rsp+60h] [rbp+18h] BYREF
  void *pDataObjInMTA; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  pDataObjInMTA = 0;
  PropW = GetPropW(hClipWnd, L"ClipboardDataObjectInterface");
  v6 = GetPropW(hClipWnd, L"ClipboardRootDataObjectInterface");
  pDataObjInMTA = GetPropW(hClipWnd, L"ClipboardDataObjectInterfaceMTA");
  v7 = (void *)SetWindowLongPtrW(hClipWnd, 0, 0);
  if ( v7 )
    HeapFree(g_hHeap, 0, v7);
  if ( (fFlags & 4) == 0 )
  {
    if ( v6 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v6 + 16LL))(v6);
    if ( pDataObjInMTA )
      RunSyncOnMTAThread__lambda_acbbe6d18a978d7bf2cb06affbc8b61b_((RemoveClipboardDataObject::__l14::<lambda_acbbe6d18a978d7bf2cb06affbc8b61b>)&pDataObjInMTA);
    if ( PropW )
    {
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)PropW + 16LL))(PropW);
      LODWORD(pData) = 0;
      dwAssignPID = 0;
      v3 = UnAssignEndpointProperty(hClipWnd, 0, (unsigned int *)&pData, &dwAssignPID);
    }
  }
  RemovePropW(hClipWnd, L"ClipboardRootDataObjectInterface");
  RemovePropW(hClipWnd, L"ClipboardDataObjectInterface");
  RemovePropW(hClipWnd, L"ClipboardDataObjectInterfaceMTA");
  if ( (fFlags & 1) != 0 && IsClipboardFormatAvailable(g_cfDataObject) )
  {
    pData = 0;
    SetFormatAsHGlobal(g_cfDataObject, &pData, 8u);
  }
  return v3;
}

```

## disassembly

```asm
0x1800255a8  push    rbx
0x1800255aa  push    rbp
0x1800255ab  push    rsi
0x1800255ac  push    rdi
0x1800255ad  push    r14
0x1800255af  sub     rsp, 20h
0x1800255b3  mov     r14d, fFlags
0x1800255b6  xor     ebp, ebp
0x1800255b8  lea     rdx, aClipboarddatao_0; "ClipboardDataObjectInterface"
0x1800255bf  mov     [rsp+48h+pDataObjInMTA], rbp
0x1800255c4  mov     rbx, hClipWnd
0x1800255c7  call    cs:__imp_GetPropW
0x1800255cd  lea     rdx, aClipboardrootd; "ClipboardRootDataObjectInterface"
0x1800255d4  mov     hClipWnd, rbx; hWnd
0x1800255d7  mov     rsi, rax
0x1800255da  call    cs:__imp_GetPropW
0x1800255e0  lea     rdx, aClipboarddatao; "ClipboardDataObjectInterfaceMTA"
0x1800255e7  mov     hClipWnd, rbx; hWnd
0x1800255ea  mov     rdi, rax
0x1800255ed  call    cs:__imp_GetPropW
0x1800255f3  xor     r8d, r8d; dwNewLong
0x1800255f6  xor     fFlags, fFlags; nIndex
0x1800255f8  mov     hClipWnd, rbx; hWnd
0x1800255fb  mov     [rsp+48h+pDataObjInMTA], rax
0x180025600  call    cs:__imp_SetWindowLongPtrW
0x180025606  test    rax, rax
0x180025609  jnz     short loc_180025658
0x18002560b  test    r14b, 4
0x18002560f  jz      short loc_18002566C
0x180025611  lea     rdx, aClipboardrootd; "ClipboardRootDataObjectInterface"
0x180025618  mov     hClipWnd, rbx; hWnd
0x18002561b  call    cs:__imp_RemovePropW
0x180025621  lea     rdx, aClipboarddatao_0; "ClipboardDataObjectInterface"
0x180025628  mov     hClipWnd, rbx; hWnd
0x18002562b  call    cs:__imp_RemovePropW
0x180025631  lea     rdx, aClipboarddatao; "ClipboardDataObjectInterfaceMTA"
0x180025638  mov     hClipWnd, rbx; hWnd
0x18002563b  call    cs:__imp_RemovePropW
0x180025641  test    r14b, 1
0x180025645  jnz     loc_1800256CC
0x18002564b  mov     eax, ebp
0x18002564d  add     rsp, 20h
0x180025651  pop     r14
0x180025653  pop     rdi
0x180025654  pop     rsi
0x180025655  pop     rbp
0x180025656  pop     rbx
0x180025657  retn
0x180025658  mov     hClipWnd, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002565f  mov     r8, rax; lpMem
0x180025662  xor     fFlags, fFlags; dwFlags
0x180025664  call    cs:__imp_HeapFree
0x18002566a  jmp     short loc_18002560B
0x18002566c  test    rdi, rdi
0x18002566f  jnz     short loc_1800256AF
0x180025671  cmp     [rsp+48h+pDataObjInMTA], rbp
0x180025676  jnz     short loc_1800256C0
0x180025678  test    rsi, rsi
0x18002567b  jz      short loc_180025611
0x18002567d  mov     rax, [rsi]
0x180025680  mov     hClipWnd, rsi
0x180025683  mov     rax, [rax+10h]
0x180025687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002568c  lea     r9, [rsp+48h+dwAssignPID]; dwAssignPID
0x180025691  mov     dword ptr [rsp+48h+pData], ebp
0x180025695  lea     r8, [rsp+48h+pData]; dwAssignAptID
0x18002569a  mov     [rsp+48h+dwAssignPID], ebp
0x18002569e  xor     fFlags, fFlags; fDragDrop
0x1800256a0  mov     hClipWnd, rbx; hWnd
0x1800256a3  call    ?UnAssignEndpointProperty@@YAJPEAUHWND__@@HPEAK1@Z; UnAssignEndpointProperty(HWND__ *,int,ulong *,ulong *)
0x1800256a8  mov     ebp, eax
0x1800256aa  jmp     loc_180025611
0x1800256af  mov     rax, [rdi]
0x1800256b2  mov     hClipWnd, rdi
0x1800256b5  mov     rax, [rax+10h]
0x1800256b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256be  jmp     short loc_180025671
0x1800256c0  lea     hClipWnd, [rsp+48h+pDataObjInMTA]; operation
0x1800256c5  call    RunSyncOnMTAThread__lambda_acbbe6d18a978d7bf2cb06affbc8b61b___; RunSyncOnMTAThread__lambda_acbbe6d18a978d7bf2cb06affbc8b61b_
0x1800256ca  jmp     short loc_180025678
0x1800256cc  movzx   ecx, cs:?g_cfDataObject@@3GA; format
0x1800256d3  call    cs:__imp_IsClipboardFormatAvailable
0x1800256d9  test    eax, eax
0x1800256db  jz      loc_18002564B
0x1800256e1  movzx   ecx, cs:?g_cfDataObject@@3GA; cfFormat
0x1800256e8  lea     rdx, [rsp+48h+pData]; pData
0x1800256ed  mov     r8d, 8; cb
0x1800256f3  mov     [rsp+48h+pData], 0
0x1800256fc  call    ?SetFormatAsHGlobal@@YAJGPEAX_K@Z; SetFormatAsHGlobal(ushort,void *,unsigned __int64)
0x180025701  jmp     loc_18002564B
```
