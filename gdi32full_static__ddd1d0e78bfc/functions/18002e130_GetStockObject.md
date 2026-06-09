# GetStockObject

- ea: `0x18002e130`
- end: `0x18002e28a`
- name: `GetStockObject`
- size: `346`
- prototype: `HGDIOBJ __stdcall(int i)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a9c`
- `0x180024c40`
- `0x180028260`
- `0x18002da00`
- `0x180035af0`
- `0x1800384e8`
- `0x1800479b0`
- `0x18005fda0`
- `0x18007def0`
- `0x18008caf0`
- `0x18008e270`
- `0x18008eb38`
- `0x180093bc4`
- `0x180095aa0`
- `0x180095bb0`
- `0x180096c50`
- `0x180096d70`

## callees

- `0x18002e130`
- `0x180070b1c`

## import_xrefs

- `GDI32!pGdiSharedMemory` at `0x18002e152`
- `GDI32!pGdiSharedMemory` at `0x18002e18c`
- `GDI32!pGdiSharedMemory` at `0x18002e1f5`
- `GDI32!pGdiSharedMemory` at `0x18002e228`
- `GDI32!pGdiSharedMemory` at `0x18002e244`
- `GDI32!pGdiSharedMemory` at `0x18002e272`
- `GDI32!GdiSetLastError` at `0x18002e21a`
- `GDI32!GdiSetLastError` at `0x18002e21a`
- `USER32!GetThreadDpiAwarenessContext` at `0x18002e146`
- `USER32!GetThreadDpiAwarenessContext` at `0x18002e1be`
- `USER32!GetThreadDpiAwarenessContext` at `0x18002e146`
- `USER32!GetThreadDpiAwarenessContext` at `0x18002e1be`
- `USER32!__imp_GetDpiForSession` at `0x18002e1d6`
- `USER32!__imp_GetDpiForSession` at `0x18002e1d6`
- `win32u!NtGdiEnsureDpiDepDefaultGuiFontForPlateau` at `0x18002e266`
- `win32u!NtGdiEnsureDpiDepDefaultGuiFontForPlateau` at `0x18002e266`

## pseudocode

```c
HGDIOBJ __stdcall GetStockObject(int i)
{
  __int64 v1; // rbx
  HGDIOBJ result; // rax
  unsigned int v3; // ebx
  unsigned int DpiForSession; // eax
  int DpiDepStockObjectPlateauSlot; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdi

  if ( (unsigned int)i > 0x15 )
    return 0;
  if ( i == 10 || i == 13 || i == 16 )
  {
    v1 = i;
    if ( (GetThreadDpiAwarenessContext() & 0xF) != 0 )
      return *(HGDIOBJ *)(pGdiSharedMemory + 8 * v1 + 1573040);
    result = *(HGDIOBJ *)(pGdiSharedMemory + 8 * v1 + 1573216);
    if ( !result )
      return *(HGDIOBJ *)(pGdiSharedMemory + 8 * v1 + 1573040);
  }
  else
  {
    if ( i != 17 )
      return *(HGDIOBJ *)(pGdiSharedMemory + 8LL * i + 1573040);
    v3 = ((unsigned int)GetThreadDpiAwarenessContext() >> 8) & 0x1FF;
    DpiForSession = GetDpiForSession();
    DpiDepStockObjectPlateauSlot = GetDpiDepStockObjectPlateauSlot(v3, DpiForSession);
    if ( DpiDepStockObjectPlateauSlot == -1 )
    {
      return *(HGDIOBJ *)(pGdiSharedMemory + 1573352LL);
    }
    else
    {
      if ( DpiDepStockObjectPlateauSlot == -2 )
        return *(HGDIOBJ *)(pGdiSharedMemory + 1573176LL);
      if ( DpiDepStockObjectPlateauSlot < 0 )
      {
        GdiSetLastError(87);
        return *(HGDIOBJ *)(pGdiSharedMemory + 1573176LL);
      }
      v6 = (_QWORD *)pGdiSharedMemory;
      v7 = 8LL * DpiDepStockObjectPlateauSlot + 1573392;
      if ( !*(_QWORD *)(v7 + pGdiSharedMemory) )
      {
        NtGdiEnsureDpiDepDefaultGuiFontForPlateau(v3);
        v6 = (_QWORD *)pGdiSharedMemory;
      }
      return *(HGDIOBJ *)(v7 + *v6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002e130  sub     rsp, 28h
0x18002e134  cmp     ecx, 15h
0x18002e137  ja      short loc_18002E173
0x18002e139  mov     [rsp+28h+arg_0], rbx
0x18002e13e  cmp     ecx, 0Ah
0x18002e141  jnz     short loc_18002E17B
0x18002e143  movsxd  rbx, ecx
0x18002e146  call    cs:__imp_GetThreadDpiAwarenessContext
0x18002e14d  nop     dword ptr [rax+rax+00h]
0x18002e152  mov     rcx, cs:__imp_pGdiSharedMemory
0x18002e159  test    al, 0Fh
0x18002e15b  jz      short loc_18002E1AC
0x18002e15d  mov     rax, [rcx]
0x18002e160  mov     rax, [rax+rbx*8+1800B0h]
0x18002e168  mov     rbx, [rsp+28h+arg_0]
0x18002e16d  add     rsp, 28h
0x18002e171  retn
0x18002e173  xor     eax, eax
0x18002e175  add     rsp, 28h
0x18002e179  retn
0x18002e17b  mov     edx, ecx
0x18002e17d  sub     edx, 0Dh
0x18002e180  jz      short loc_18002E143
0x18002e182  sub     edx, 3
0x18002e185  jz      short loc_18002E143
0x18002e187  cmp     edx, 1
0x18002e18a  jz      short loc_18002E1BE
0x18002e18c  mov     rax, cs:__imp_pGdiSharedMemory
0x18002e193  mov     rbx, [rsp+28h+arg_0]
0x18002e198  movsxd  rdx, ecx
0x18002e19b  mov     rcx, [rax]
0x18002e19e  mov     rax, [rcx+rdx*8+1800B0h]
0x18002e1a6  add     rsp, 28h
0x18002e1aa  retn
0x18002e1ac  mov     rax, [rcx]
0x18002e1af  mov     rax, [rax+rbx*8+180160h]
0x18002e1b7  test    rax, rax
0x18002e1ba  jz      short loc_18002E15D
0x18002e1bc  jmp     short loc_18002E168
0x18002e1be  call    cs:__imp_GetThreadDpiAwarenessContext
0x18002e1c5  nop     dword ptr [rax+rax+00h]
0x18002e1ca  mov     rbx, rax
0x18002e1cd  shr     ebx, 8
0x18002e1d0  and     ebx, 1FFh
0x18002e1d6  call    cs:__imp_GetDpiForSession
0x18002e1dd  nop     dword ptr [rax+rax+00h]
0x18002e1e2  mov     edx, eax
0x18002e1e4  mov     ecx, ebx
0x18002e1e6  call    GetDpiDepStockObjectPlateauSlot
0x18002e1eb  cmp     eax, 0FFFFFFFFh
0x18002e1ee  jz      short loc_18002E228
0x18002e1f0  cmp     eax, 0FFFFFFFEh
0x18002e1f3  jnz     short loc_18002E211
0x18002e1f5  mov     rax, cs:__imp_pGdiSharedMemory
0x18002e1fc  mov     rbx, [rsp+28h+arg_0]
0x18002e201  mov     rcx, [rax]
0x18002e204  mov     rax, [rcx+180138h]
0x18002e20b  add     rsp, 28h
0x18002e20f  retn
0x18002e211  test    eax, eax
0x18002e213  jns     short loc_18002E244
0x18002e215  mov     ecx, 57h ; 'W'
0x18002e21a  call    cs:__imp_GdiSetLastError
0x18002e221  nop     dword ptr [rax+rax+00h]
0x18002e226  jmp     short loc_18002E1F5
0x18002e228  mov     rax, cs:__imp_pGdiSharedMemory
0x18002e22f  mov     rbx, [rsp+28h+arg_0]
0x18002e234  mov     rcx, [rax]
0x18002e237  mov     rax, [rcx+1801E8h]
0x18002e23e  add     rsp, 28h
0x18002e242  retn
0x18002e244  mov     rcx, cs:__imp_pGdiSharedMemory
0x18002e24b  cdqe
0x18002e24d  mov     [rsp+28h+var_8], rdi
0x18002e252  lea     rdi, ds:180210h[rax*8]
0x18002e25a  mov     rax, [rcx]
0x18002e25d  cmp     qword ptr [rdi+rax], 0
0x18002e262  jnz     short loc_18002E279
0x18002e264  mov     ecx, ebx
0x18002e266  call    cs:__imp_NtGdiEnsureDpiDepDefaultGuiFontForPlateau
0x18002e26d  nop     dword ptr [rax+rax+00h]
0x18002e272  mov     rcx, cs:__imp_pGdiSharedMemory
0x18002e279  mov     rax, [rcx]
0x18002e27c  mov     rax, [rdi+rax]
0x18002e280  mov     rdi, [rsp+28h+var_8]
0x18002e285  jmp     loc_18002E168
```
