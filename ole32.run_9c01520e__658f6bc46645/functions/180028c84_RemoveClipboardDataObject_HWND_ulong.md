# RemoveClipboardDataObject(HWND__ *,ulong)

- ea: `0x180028c84`
- end: `0x180028e15`
- name: `?RemoveClipboardDataObject@@YAJPEAUHWND__@@K@Z`
- size: `401`
- prototype: `HRESULT __fastcall(HWND__ *hClipWnd, unsigned int fFlags)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001c654`
- `0x180028b40`

## callees

- `0x18000a8f0`
- `0x18000c078`
- `0x180028c84`
- `0x180087698`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028d66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028d66`
- `USER32!SetWindowLongPtrW` at `0x180028ce9`
- `USER32!SetWindowLongPtrW` at `0x180028ce9`
- `USER32!GetPropW` at `0x180028c9e`
- `USER32!GetPropW` at `0x180028cb7`
- `USER32!GetPropW` at `0x180028cd0`
- `USER32!GetPropW` at `0x180028c9e`
- `USER32!GetPropW` at `0x180028cb7`
- `USER32!GetPropW` at `0x180028cd0`
- `USER32!IsClipboardFormatAvailable` at `0x180028ddf`
- `USER32!IsClipboardFormatAvailable` at `0x180028ddf`
- `USER32!RemovePropW` at `0x180028d0a`
- `USER32!RemovePropW` at `0x180028d20`
- `USER32!RemovePropW` at `0x180028d36`
- `USER32!RemovePropW` at `0x180028d0a`
- `USER32!RemovePropW` at `0x180028d20`
- `USER32!RemovePropW` at `0x180028d36`

## pseudocode

```c
__int64 __fastcall RemoveClipboardDataObject(HWND hClipWnd, char fFlags)
{
  unsigned int v4; // ebp
  HANDLE PropW; // rsi
  HANDLE v6; // rdi
  void *v7; // rax
  unsigned int dwAssignPID; // [rsp+58h] [rbp+10h] BYREF
  IDataObject *pData; // [rsp+60h] [rbp+18h] BYREF
  void *pDataObjInMTA; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
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
      v4 = UnAssignEndpointProperty(hClipWnd, 0, (unsigned int *)&pData, &dwAssignPID);
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
  return v4;
}

```

## disassembly

```asm
0x180028c84  push    rbx
0x180028c86  push    rbp
0x180028c87  push    rsi
0x180028c88  push    rdi
0x180028c89  push    r14
0x180028c8b  sub     rsp, 20h
0x180028c8f  mov     r14d, fFlags
0x180028c92  mov     rbx, hClipWnd
0x180028c95  lea     rdx, aClipboarddatao_0; "ClipboardDataObjectInterface"
0x180028c9c  xor     ebp, ebp
0x180028c9e  call    cs:__imp_GetPropW
0x180028ca5  nop     dword ptr [rax+rax+00h]
0x180028caa  lea     rdx, aClipboardrootd; "ClipboardRootDataObjectInterface"
0x180028cb1  mov     hClipWnd, rbx; hWnd
0x180028cb4  mov     rsi, rax
0x180028cb7  call    cs:__imp_GetPropW
0x180028cbe  nop     dword ptr [rax+rax+00h]
0x180028cc3  lea     rdx, aClipboarddatao; "ClipboardDataObjectInterfaceMTA"
0x180028cca  mov     hClipWnd, rbx; hWnd
0x180028ccd  mov     rdi, rax
0x180028cd0  call    cs:__imp_GetPropW
0x180028cd7  nop     dword ptr [rax+rax+00h]
0x180028cdc  xor     r8d, r8d; dwNewLong
0x180028cdf  xor     fFlags, fFlags; nIndex
0x180028ce1  mov     hClipWnd, rbx; hWnd
0x180028ce4  mov     [rsp+48h+pDataObjInMTA], rax
0x180028ce9  call    cs:__imp_SetWindowLongPtrW
0x180028cf0  nop     dword ptr [rax+rax+00h]
0x180028cf5  test    rax, rax
0x180028cf8  jnz     short loc_180028D5A
0x180028cfa  test    r14b, 4
0x180028cfe  jz      short loc_180028D74
0x180028d00  lea     rdx, aClipboardrootd; "ClipboardRootDataObjectInterface"
0x180028d07  mov     hClipWnd, rbx; hWnd
0x180028d0a  call    cs:__imp_RemovePropW
0x180028d11  nop     dword ptr [rax+rax+00h]
0x180028d16  lea     rdx, aClipboarddatao_0; "ClipboardDataObjectInterface"
0x180028d1d  mov     hClipWnd, rbx; hWnd
0x180028d20  call    cs:__imp_RemovePropW
0x180028d27  nop     dword ptr [rax+rax+00h]
0x180028d2c  lea     rdx, aClipboarddatao; "ClipboardDataObjectInterfaceMTA"
0x180028d33  mov     hClipWnd, rbx; hWnd
0x180028d36  call    cs:__imp_RemovePropW
0x180028d3d  nop     dword ptr [rax+rax+00h]
0x180028d42  test    r14b, 1
0x180028d46  jnz     loc_180028DD8
0x180028d4c  mov     eax, ebp
0x180028d4e  add     rsp, 20h
0x180028d52  pop     r14
0x180028d54  pop     rdi
0x180028d55  pop     rsi
0x180028d56  pop     rbp
0x180028d57  pop     rbx
0x180028d58  retn
0x180028d5a  mov     hClipWnd, cs:?g_hHeap@@3QEAXEA; hHeap
0x180028d61  mov     r8, rax; lpMem
0x180028d64  xor     fFlags, fFlags; dwFlags
0x180028d66  call    cs:__imp_HeapFree
0x180028d6d  nop     dword ptr [rax+rax+00h]
0x180028d72  jmp     short loc_180028CFA
0x180028d74  test    rdi, rdi
0x180028d77  jnz     short loc_180028DBB
0x180028d79  cmp     [rsp+48h+pDataObjInMTA], rbp
0x180028d7e  jnz     short loc_180028DCC
0x180028d80  test    rsi, rsi
0x180028d83  jz      loc_180028D00
0x180028d89  mov     rax, [rsi]
0x180028d8c  mov     hClipWnd, rsi
0x180028d8f  mov     rax, [rax+10h]
0x180028d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d98  and     dword ptr [rsp+48h+pData], ebp
0x180028d9c  lea     r9, [rsp+48h+dwAssignPID]; dwAssignPID
0x180028da1  and     [rsp+48h+dwAssignPID], ebp
0x180028da5  lea     r8, [rsp+48h+pData]; dwAssignAptID
0x180028daa  xor     fFlags, fFlags; fDragDrop
0x180028dac  mov     hClipWnd, rbx; hWnd
0x180028daf  call    ?UnAssignEndpointProperty@@YAJPEAUHWND__@@HPEAK1@Z; UnAssignEndpointProperty(HWND__ *,int,ulong *,ulong *)
0x180028db4  mov     ebp, eax
0x180028db6  jmp     loc_180028D00
0x180028dbb  mov     rax, [rdi]
0x180028dbe  mov     hClipWnd, rdi
0x180028dc1  mov     rax, [rax+10h]
0x180028dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028dca  jmp     short loc_180028D79
0x180028dcc  lea     hClipWnd, [rsp+48h+pDataObjInMTA]; operation
0x180028dd1  call    RunSyncOnMTAThread__lambda_acbbe6d18a978d7bf2cb06affbc8b61b___; RunSyncOnMTAThread__lambda_acbbe6d18a978d7bf2cb06affbc8b61b_
0x180028dd6  jmp     short loc_180028D80
0x180028dd8  movzx   ecx, cs:?g_cfDataObject@@3GA; format
0x180028ddf  call    cs:__imp_IsClipboardFormatAvailable
0x180028de6  nop     dword ptr [rax+rax+00h]
0x180028deb  test    eax, eax
0x180028ded  jz      loc_180028D4C
0x180028df3  and     [rsp+48h+pData], 0
0x180028df9  lea     rdx, [rsp+48h+pData]; pData
0x180028dfe  movzx   ecx, cs:?g_cfDataObject@@3GA; cfFormat
0x180028e05  mov     r8d, 8; cb
0x180028e0b  call    ?SetFormatAsHGlobal@@YAJGPEAX_K@Z; SetFormatAsHGlobal(ushort,void *,unsigned __int64)
0x180028e10  jmp     loc_180028D4C
```
