# CFtpProp_DoProp(CFtpPidlList *,CFtpFolder *,HWND__ *)

- ea: `0x18001e420`
- end: `0x18001e500`
- name: `?CFtpProp_DoProp@@YAJPEAVCFtpPidlList@@PEAVCFtpFolder@@PEAUHWND__@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(struct CFtpPidlList *, struct CFtpFolder *, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000e4c0`

## callees

- `0x18001e420`
- `0x180023adc`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e4c4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e4c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e4d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e4d2`

## pseudocode

```c
__int64 __fastcall CFtpProp_DoProp(struct CFtpPidlList *a1, struct CFtpFolder *a2, HWND a3)
{
  _DWORD *v6; // rbx
  HANDLE v7; // rax
  DWORD ThreadId; // [rsp+78h] [rbp+20h] BYREF

  v6 = operator new(0x38u);
  if ( !v6 )
    return 2147942414LL;
  v6[2] = 1;
  *(_QWORD *)v6 = &CFtpProp::`vftable';
  _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
  *((_QWORD *)v6 + 3) = 0;
  *((_QWORD *)v6 + 2) = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct CFtpFolder *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_QWORD *)v6 + 3) = a1;
  if ( a1 )
    (*(void (__fastcall **)(struct CFtpPidlList *))(*(_QWORD *)a1 + 8LL))(a1);
  *((_QWORD *)v6 + 4) = a3;
  ThreadId = 0;
  v7 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CFtpProp::_PropertySheetThreadProc, v6, 0, &ThreadId);
  if ( v7 )
  {
    CloseHandle(v7);
    return 0;
  }
  else
  {
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18001e420  push    rbx
0x18001e422  push    rbp
0x18001e423  push    rsi
0x18001e424  push    rdi
0x18001e425  sub     rsp, 38h
0x18001e429  mov     rdi, rcx
0x18001e42c  mov     rbp, r8
0x18001e42f  mov     ecx, 38h ; '8'; unsigned __int64
0x18001e434  mov     rsi, rdx
0x18001e437  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e43c  mov     rbx, rax
0x18001e43f  test    rax, rax
0x18001e442  jz      loc_18001E4F2
0x18001e448  lea     rax, ??_7CFtpProp@@6B@; const CFtpProp::`vftable'
0x18001e44f  mov     dword ptr [rbx+8], 1
0x18001e456  mov     [rbx], rax
0x18001e459  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x18001e460  mov     qword ptr [rbx+18h], 0
0x18001e468  mov     [rbx+10h], rsi
0x18001e46c  test    rsi, rsi
0x18001e46f  jz      short loc_18001E480
0x18001e471  mov     rax, [rsi]
0x18001e474  mov     rcx, rsi
0x18001e477  mov     rax, [rax+8]
0x18001e47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e480  mov     [rbx+18h], rdi
0x18001e484  test    rdi, rdi
0x18001e487  jz      short loc_18001E498
0x18001e489  mov     rax, [rdi]
0x18001e48c  mov     rcx, rdi
0x18001e48f  mov     rax, [rax+8]
0x18001e493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e498  lea     rax, [rsp+58h+ThreadId]
0x18001e49d  mov     [rbx+20h], rbp
0x18001e4a1  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18001e4a6  lea     r8, ?_PropertySheetThreadProc@CFtpProp@@SAKPEAX@Z; lpStartAddress
0x18001e4ad  mov     r9, rbx; lpParameter
0x18001e4b0  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18001e4b8  xor     edx, edx; dwStackSize
0x18001e4ba  mov     [rsp+58h+ThreadId], 0
0x18001e4c2  xor     ecx, ecx; lpThreadAttributes
0x18001e4c4  call    cs:__imp_CreateThread
0x18001e4ca  test    rax, rax
0x18001e4cd  jz      short loc_18001E4DC
0x18001e4cf  mov     rcx, rax; hObject
0x18001e4d2  call    cs:__imp_CloseHandle
0x18001e4d8  xor     eax, eax
0x18001e4da  jmp     short loc_18001E4F7
0x18001e4dc  mov     rax, [rbx]
0x18001e4df  mov     rcx, rbx
0x18001e4e2  mov     rax, [rax+10h]
0x18001e4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4eb  mov     eax, 8000FFFFh
0x18001e4f0  jmp     short loc_18001E4F7
0x18001e4f2  mov     eax, 8007000Eh
0x18001e4f7  add     rsp, 38h
0x18001e4fb  pop     rdi
0x18001e4fc  pop     rsi
0x18001e4fd  pop     rbp
0x18001e4fe  pop     rbx
0x18001e4ff  retn
```
