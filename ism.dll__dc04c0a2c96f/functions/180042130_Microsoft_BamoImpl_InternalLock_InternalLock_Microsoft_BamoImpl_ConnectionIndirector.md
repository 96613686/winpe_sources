# Microsoft::BamoImpl::InternalLock::InternalLock(Microsoft::BamoImpl::ConnectionIndirector *)

- ea: `0x180042130`
- end: `0x1800421aa`
- name: `??0InternalLock@BamoImpl@Microsoft@@QEAA@PEAVConnectionIndirector@12@@Z`
- size: `122`
- prototype: `__int64 __fastcall(Microsoft::BamoImpl::InternalLock *__hidden this, struct Microsoft::BamoImpl::ConnectionIndirector *)`
- caller_count: `329`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800114b0`
- `0x180012628`
- `0x180039ba0`
- `0x180039e00`
- `0x180039e50`
- `0x180039ea0`
- `0x180040890`
- `0x180040cf0`
- `0x180040e20`
- `0x180041250`
- `0x180041290`
- `0x1800421b0`
- `0x180049530`
- `0x180061120`
- `0x18006141c`
- `0x180072f60`
- `0x180074a70`
- `0x1800752c0`
- `0x180079200`
- `0x180079700`
- `0x18007a0c0`
- `0x18007c7b0`
- `0x18007c830`
- `0x18007ce80`
- `0x18007d510`
- `0x18007f400`
- `0x18007f6d0`
- `0x1800807a0`
- `0x180081250`
- `0x1800833a0`
- `0x1800833f0`
- `0x18009f2b0`
- `0x18009ff50`
- `0x1800a01a0`
- `0x1800a0340`
- `0x1800a04e0`
- `0x1800a0680`
- `0x1800a0788`
- `0x1800a0840`
- `0x1800a09e0`
- `0x1800a0c00`
- `0x1800a0da0`
- `0x1800a0f40`
- `0x1800a2150`
- `0x1800a4cf0`
- `0x1800ab3a0`
- `0x1800afda0`
- `0x1800affa0`
- `0x1800b0010`
- `0x1800b2200`

## callees

- `0x180042130`
- `0x180043720`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042155`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042182`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042155`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042182`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Microsoft::BamoImpl::InternalLock *__fastcall Microsoft::BamoImpl::InternalLock::InternalLock(
        Microsoft::BamoImpl::BamoImplObject **this,
        struct Microsoft::BamoImpl::ConnectionIndirector *a2)
{
  __int64 v4; // rsi
  Microsoft::BamoImpl::BamoImplObject *v5; // rcx

  *this = 0;
  v4 = *((_QWORD *)a2 + 4);
  if ( *(_DWORD *)(v4 + 184) != GetCurrentThreadId() )
  {
    v5 = *this;
    *this = a2;
    _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
    if ( v5 )
      Microsoft::BamoImpl::BamoImplObject::Release(v5);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 16) + 24LL))(*(_QWORD *)(v4 + 16));
    *(_DWORD *)(v4 + 184) = GetCurrentThreadId();
  }
  return (Microsoft::BamoImpl::InternalLock *)this;
}

```

## disassembly

```asm
0x180042130  mov     [rsp+arg_8], rbx
0x180042135  mov     [rsp+arg_10], rsi
0x18004213a  mov     [rsp+arg_0], rcx
0x18004213f  push    rdi
0x180042140  sub     rsp, 20h
0x180042144  mov     rbx, rdx
0x180042147  mov     rdi, rcx
0x18004214a  mov     qword ptr [rcx], 0
0x180042151  mov     rsi, [rdx+20h]
0x180042155  call    cs:__imp_GetCurrentThreadId
0x18004215b  cmp     [rsi+0B8h], eax
0x180042161  jz      short loc_18004218E
0x180042163  mov     rcx, [rdi]; this
0x180042166  mov     [rdi], rbx
0x180042169  lock inc dword ptr [rbx+8]
0x18004216d  test    rcx, rcx
0x180042170  jnz     short loc_1800421A1
0x180042172  mov     rcx, [rsi+10h]
0x180042176  mov     rax, [rcx]
0x180042179  mov     rax, [rax+18h]
0x18004217d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042182  call    cs:__imp_GetCurrentThreadId
0x180042188  mov     [rsi+0B8h], eax
0x18004218e  mov     rax, rdi
0x180042191  mov     rbx, [rsp+28h+arg_8]
0x180042196  mov     rsi, [rsp+28h+arg_10]
0x18004219b  add     rsp, 20h
0x18004219f  pop     rdi
0x1800421a0  retn
0x1800421a1  call    ?Release@BamoImplObject@BamoImpl@Microsoft@@UEAAKXZ; Microsoft::BamoImpl::BamoImplObject::Release(void)
0x1800421a6  nop
0x1800421a7  jmp     short loc_180042172
```
