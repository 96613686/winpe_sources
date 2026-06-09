# dllmain_crt_dispatch

- ea: `0x18000bad0`
- end: `0x18000bb20`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000bcb4`

## callees

- `0x18000bad0`
- `0x18000bb28`
- `0x18000bc28`
- `0x18000bef0`
- `0x18000bf20`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( !a2 )
    return dllmain_crt_process_detach(a3 != 0);
  v3 = a2 - 1;
  if ( !v3 )
    return dllmain_crt_process_attach(a1, a3);
  v4 = v3 - 1;
  if ( v4 )
  {
    if ( v4 != 1 )
      return 1;
    LOBYTE(result) = _scrt_dllmain_crt_thread_detach();
  }
  else
  {
    LOBYTE(result) = _scrt_dllmain_crt_thread_attach();
  }
  return (unsigned __int8)result;
}

```

## disassembly

```asm
0x18000bad0  sub     rsp, 28h
0x18000bad4  test    edx, edx
0x18000bad6  jz      short loc_18000BB11
0x18000bad8  sub     edx, 1
0x18000badb  jz      short loc_18000BB05
0x18000badd  sub     edx, 1
0x18000bae0  jz      short loc_18000BAF8
0x18000bae2  cmp     edx, 1
0x18000bae5  jz      short loc_18000BAF1
0x18000bae7  mov     eax, 1
0x18000baec  add     rsp, 28h
0x18000baf0  retn
0x18000baf1  call    __scrt_dllmain_crt_thread_detach
0x18000baf6  jmp     short loc_18000BAFD
0x18000baf8  call    __scrt_dllmain_crt_thread_attach
0x18000bafd  movzx   eax, al
0x18000bb00  add     rsp, 28h
0x18000bb04  retn
0x18000bb05  mov     rdx, r8
0x18000bb08  add     rsp, 28h
0x18000bb0c  jmp     dllmain_crt_process_attach
0x18000bb11  test    r8, r8
0x18000bb14  setnz   cl
0x18000bb17  add     rsp, 28h
0x18000bb1b  jmp     dllmain_crt_process_detach
```
