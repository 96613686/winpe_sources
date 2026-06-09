# NMP_ConnectNamedPipe(NMP_ADDRESS *)

- ea: `0x180060fec`
- end: `0x180061084`
- name: `?NMP_ConnectNamedPipe@@YAJPEAUNMP_ADDRESS@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(struct NMP_ADDRESS *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005fd90`

## callees

- `0x18005b4c8`
- `0x180060fec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061029`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x18006101f`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x18006101f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180061007`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180061007`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180061057`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180061057`

## pseudocode

```c
__int64 __fastcall NMP_ConnectNamedPipe(struct NMP_ADDRESS *a1)
{
  DWORD LastError; // ebx

  StartThreadpoolIo(**(PTP_IO **)(*((_QWORD *)a1 + 25) + 48LL));
  if ( ConnectNamedPipe(*(HANDLE *)(*((_QWORD *)a1 + 25) + 56LL), (LPOVERLAPPED)((char *)a1 + 136)) )
  {
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      CancelThreadpoolIo(**(PTP_IO **)(*((_QWORD *)a1 + 25) + 48LL));
      if ( LastError == 232 )
      {
        NMP_FreePipeInstance(a1, *((struct NMP_PIPE_INSTANCE **)a1 + 25), 0);
        *((_QWORD *)a1 + 25) = 0;
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180060fec  mov     [rsp+arg_0], rbx
0x180060ff1  push    rdi
0x180060ff2  sub     rsp, 20h
0x180060ff6  mov     rax, [rcx+0C8h]
0x180060ffd  mov     rdi, rcx
0x180061000  mov     rcx, [rax+30h]
0x180061004  mov     rcx, [rcx]; pio
0x180061007  call    cs:__imp_StartThreadpoolIo
0x18006100d  mov     rcx, [rdi+0C8h]
0x180061014  lea     rdx, [rdi+88h]; lpOverlapped
0x18006101b  mov     rcx, [rcx+38h]; hNamedPipe
0x18006101f  call    cs:__imp_ConnectNamedPipe
0x180061025  test    eax, eax
0x180061027  jnz     short loc_180061045
0x180061029  call    cs:__imp_GetLastError
0x18006102f  mov     ebx, eax
0x180061031  cmp     eax, 3E5h
0x180061036  jnz     short loc_180061049
0x180061038  mov     eax, ebx
0x18006103a  mov     rbx, [rsp+28h+arg_0]
0x18006103f  add     rsp, 20h
0x180061043  pop     rdi
0x180061044  retn
0x180061045  xor     ebx, ebx
0x180061047  jmp     short loc_180061038
0x180061049  mov     rcx, [rdi+0C8h]
0x180061050  mov     rcx, [rcx+30h]
0x180061054  mov     rcx, [rcx]; pio
0x180061057  call    cs:__imp_CancelThreadpoolIo
0x18006105d  cmp     ebx, 0E8h
0x180061063  jnz     short loc_180061038
0x180061065  mov     rdx, [rdi+0C8h]; struct NMP_PIPE_INSTANCE *
0x18006106c  xor     r8d, r8d; int
0x18006106f  mov     rcx, rdi; struct NMP_ADDRESS *
0x180061072  call    ?NMP_FreePipeInstance@@YAXPEAUNMP_ADDRESS@@PEAVNMP_PIPE_INSTANCE@@H@Z; NMP_FreePipeInstance(NMP_ADDRESS *,NMP_PIPE_INSTANCE *,int)
0x180061077  mov     qword ptr [rdi+0C8h], 0
0x180061082  jmp     short loc_180061038
```
