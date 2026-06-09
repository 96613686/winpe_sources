# RasSrvStopService

- ea: `0x180020240`
- end: `0x1800202d8`
- name: `RasSrvStopService`
- size: `152`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18001ffac`

## callees

- `0x180020240`
- `0x180020b80`
- `0x180021274`
- `0x1800213fc`
- `0x1800263f8`
- `0x1800264b4`
- `0x18002663c`

## import_xrefs

- `USER32!GetActiveWindow` at `0x180020288`
- `USER32!GetActiveWindow` at `0x180020288`

## string_xrefs

- `0x180020270`: `remoteaccess`

## pseudocode

```c
__int64 __fastcall RasSrvStopService(__int64 lpMem)
{
  SC_HANDLE *v1; // rbx
  int v2; // esi
  __int64 result; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // edi
  SC_HANDLE *v7; // [rsp+30h] [rbp+8h] BYREF
  HCURSOR hCursor; // [rsp+38h] [rbp+10h] BYREF

  v7 = (SC_HANDLE *)lpMem;
  v1 = (SC_HANDLE *)lpMem;
  hCursor = 0;
  v2 = 0;
  RasSrvUiInit();
  if ( !v1 )
  {
    result = DialupOpenNamedService(aRemoteaccess, (__int64 *)&v7);
    if ( (_DWORD)result )
      return result;
    v2 = 1;
    v1 = v7;
  }
  GetActiveWindow();
  RasSrvShowServiceWait(v5, v4, &hCursor);
  v6 = SvcStop((__int64)v1);
  if ( v6 == 1460 )
    v6 = 1003;
  RasSrvFinishServiceWait(hCursor);
  if ( v2 )
    SvcClose(v1);
  return v6;
}

```

## disassembly

```asm
0x180020240  mov     rax, rsp
0x180020243  mov     [rax+18h], rbx
0x180020247  mov     [rax+20h], rsi
0x18002024b  mov     [rax+8], rcx
0x18002024f  push    rdi
0x180020250  sub     rsp, 20h
0x180020254  mov     rbx, rcx
0x180020257  mov     qword ptr [rax+10h], 0
0x18002025f  xor     esi, esi
0x180020261  call    RasSrvUiInit
0x180020266  test    rbx, rbx
0x180020269  jnz     short loc_180020288
0x18002026b  lea     rdx, [rsp+28h+arg_0]
0x180020270  lea     rcx, aRemoteaccess; "remoteaccess"
0x180020277  call    DialupOpenNamedService
0x18002027c  test    eax, eax
0x18002027e  jnz     short loc_1800202C8
0x180020280  lea     esi, [rbx+1]
0x180020283  mov     rbx, [rsp+28h+arg_0]
0x180020288  call    cs:__imp_GetActiveWindow
0x18002028e  lea     r8, [rsp+28h+hCursor]
0x180020293  call    RasSrvShowServiceWait
0x180020298  mov     rcx, rbx
0x18002029b  call    SvcStop
0x1800202a0  mov     rcx, [rsp+28h+hCursor]; hCursor
0x1800202a5  mov     edi, eax
0x1800202a7  mov     eax, 3EBh
0x1800202ac  cmp     edi, 5B4h
0x1800202b2  cmovz   edi, eax
0x1800202b5  call    RasSrvFinishServiceWait
0x1800202ba  test    esi, esi
0x1800202bc  jz      short loc_1800202C6
0x1800202be  mov     rcx, rbx; lpMem
0x1800202c1  call    SvcClose
0x1800202c6  mov     eax, edi
0x1800202c8  mov     rbx, [rsp+28h+arg_10]
0x1800202cd  mov     rsi, [rsp+28h+arg_18]
0x1800202d2  add     rsp, 20h
0x1800202d6  pop     rdi
0x1800202d7  retn
```
