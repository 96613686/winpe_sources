# AsyncWorkReadyCallback

- ea: `0x140004cb0`
- end: `0x140004d6c`
- name: `AsyncWorkReadyCallback`
- size: `188`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PVOID Overlapped, ULONG IoResult)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x140001a80`
- `0x140004cb0`
- `0x140004fbc`
- `0x140005044`
- `0x140005295`

## import_xrefs

- `ntdll!NtFreeVirtualMemory` at `0x140004d4d`
- `ntdll!NtFreeVirtualMemory` at `0x140004d4d`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x140004d0b`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x140004d0b`

## pseudocode

```c
void __fastcall AsyncWorkReadyCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PVOID Overlapped, ULONG IoResult)
{
  unsigned int *v4; // rdi
  unsigned int v5; // esi
  unsigned int *v6; // rbx
  void *LsaHeap; // rax
  void *v8; // rbp
  ULONG_PTR RegionSize[7]; // [rsp+20h] [rbp-38h] BYREF

  if ( !IoResult )
  {
    v4 = (unsigned int *)OutBuffer;
    if ( OutBuffer )
    {
      v5 = 0;
      v6 = (unsigned int *)((char *)OutBuffer + 4);
      if ( *(_DWORD *)OutBuffer )
      {
        do
        {
          LsaHeap = (void *)LsapAllocateLsaHeap(v6[10], Context, Overlapped);
          v8 = LsaHeap;
          if ( !LsaHeap
            || (memcpy_0(LsaHeap, v6, v6[10]),
                !TrySubmitThreadpoolCallback((PTP_SIMPLE_CALLBACK)AsyncWorkerThreadCallback, v8, &pcbe)) )
          {
            SendStatusOnlyResponse(v6, 3221225626LL);
          }
          ++v5;
          v6 = (unsigned int *)((char *)v6 + v6[10]);
        }
        while ( v5 < *v4 );
      }
      RegionSize[0] = 0;
      NtFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &OutBuffer, RegionSize, 0x8000u);
      OutBuffer = 0;
      SendRequestForNextAsyncKsecddCall();
    }
  }
}

```

## disassembly

```asm
0x140004cb0  test    r9d, r9d
0x140004cb3  jnz     locret_140004D6B
0x140004cb9  push    rbx
0x140004cba  push    rbp
0x140004cbb  push    rsi
0x140004cbc  push    rdi
0x140004cbd  sub     rsp, 38h
0x140004cc1  mov     rdi, cs:OutBuffer
0x140004cc8  test    rdi, rdi
0x140004ccb  jz      loc_140004D63
0x140004cd1  xor     esi, esi
0x140004cd3  lea     rbx, [rdi+4]
0x140004cd7  cmp     [rdi], esi
0x140004cd9  jbe     short loc_140004D2E
0x140004cdb  mov     ecx, [rbx+28h]
0x140004cde  call    LsapAllocateLsaHeap
0x140004ce3  mov     rbp, rax
0x140004ce6  test    rax, rax
0x140004ce9  jz      short loc_140004D15
0x140004ceb  mov     r8d, [rbx+28h]; Size
0x140004cef  mov     rdx, rbx; Src
0x140004cf2  mov     rcx, rax; void *
0x140004cf5  call    memcpy_0
0x140004cfa  lea     r8, pcbe; pcbe
0x140004d01  mov     rdx, rbp; pv
0x140004d04  lea     rcx, AsyncWorkerThreadCallback; pfns
0x140004d0b  call    cs:__imp_TrySubmitThreadpoolCallback
0x140004d11  test    eax, eax
0x140004d13  jnz     short loc_140004D22
0x140004d15  mov     edx, 0C000009Ah
0x140004d1a  mov     rcx, rbx
0x140004d1d  call    SendStatusOnlyResponse
0x140004d22  mov     eax, [rbx+28h]
0x140004d25  inc     esi
0x140004d27  add     rbx, rax
0x140004d2a  cmp     esi, [rdi]
0x140004d2c  jb      short loc_140004CDB
0x140004d2e  mov     r9d, 8000h; FreeType
0x140004d34  mov     [rsp+58h+RegionSize], 0
0x140004d3d  lea     r8, [rsp+58h+RegionSize]; RegionSize
0x140004d42  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140004d46  lea     rdx, OutBuffer; BaseAddress
0x140004d4d  call    cs:__imp_NtFreeVirtualMemory
0x140004d53  mov     cs:OutBuffer, 0
0x140004d5e  call    SendRequestForNextAsyncKsecddCall
0x140004d63  add     rsp, 38h
0x140004d67  pop     rdi
0x140004d68  pop     rsi
0x140004d69  pop     rbp
0x140004d6a  pop     rbx
0x140004d6b  retn
```
