# GetStockObject

- ea: `0x180025090`
- end: `0x1800251c7`
- name: `GetStockObject`
- size: `311`
- prototype: `HGDIOBJ __stdcall(int i)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x180011fc0`
- `0x18001da40`
- `0x18001ec70`
- `0x1800249a0`
- `0x180032694`
- `0x18003bd30`
- `0x18005421c`
- `0x18005ba70`
- `0x180079350`
- `0x1800876a0`
- `0x180088cd4`
- `0x180089514`
- `0x18008e274`
- `0x180090020`
- `0x180090120`
- `0x1800910f0`
- `0x180091210`

## callees

- `0x180025090`
- `0x18006c19c`

## import_xrefs

- `GDI32!pGdiSharedMemory` at `0x1800250ac`
- `GDI32!pGdiSharedMemory` at `0x1800250e4`
- `GDI32!pGdiSharedMemory` at `0x180025140`
- `GDI32!pGdiSharedMemory` at `0x18002516c`
- `GDI32!pGdiSharedMemory` at `0x180025187`
- `GDI32!pGdiSharedMemory` at `0x1800251af`
- `GDI32!GdiSetLastError` at `0x180025164`
- `GDI32!GdiSetLastError` at `0x180025164`
- `USER32!GetThreadDpiAwarenessContext` at `0x1800250a6`
- `USER32!GetThreadDpiAwarenessContext` at `0x180025115`
- `USER32!GetThreadDpiAwarenessContext` at `0x1800250a6`
- `USER32!GetThreadDpiAwarenessContext` at `0x180025115`
- `USER32!__imp_GetDpiForSession` at `0x180025127`
- `USER32!__imp_GetDpiForSession` at `0x180025127`
- `win32u!NtGdiEnsureDpiDepDefaultGuiFontForPlateau` at `0x1800251a9`
- `win32u!NtGdiEnsureDpiDepDefaultGuiFontForPlateau` at `0x1800251a9`

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
0x180025090  sub     rsp, 28h
0x180025094  cmp     ecx, 15h
0x180025097  ja      short loc_1800250CC
0x180025099  mov     [rsp+28h+arg_0], rbx
0x18002509e  cmp     ecx, 0Ah
0x1800250a1  jnz     short loc_1800250D3
0x1800250a3  movsxd  rbx, ecx
0x1800250a6  call    cs:__imp_GetThreadDpiAwarenessContext
0x1800250ac  mov     rcx, cs:__imp_pGdiSharedMemory
0x1800250b3  test    al, 0Fh
0x1800250b5  jz      short loc_180025103
0x1800250b7  mov     rax, [rcx]
0x1800250ba  mov     rax, [rax+rbx*8+1800B0h]
0x1800250c2  mov     rbx, [rsp+28h+arg_0]
0x1800250c7  add     rsp, 28h
0x1800250cb  retn
0x1800250cc  xor     eax, eax
0x1800250ce  add     rsp, 28h
0x1800250d2  retn
0x1800250d3  mov     edx, ecx
0x1800250d5  sub     edx, 0Dh
0x1800250d8  jz      short loc_1800250A3
0x1800250da  sub     edx, 3
0x1800250dd  jz      short loc_1800250A3
0x1800250df  cmp     edx, 1
0x1800250e2  jz      short loc_180025115
0x1800250e4  mov     rax, cs:__imp_pGdiSharedMemory
0x1800250eb  mov     rbx, [rsp+28h+arg_0]
0x1800250f0  movsxd  rdx, ecx
0x1800250f3  mov     rcx, [rax]
0x1800250f6  mov     rax, [rcx+rdx*8+1800B0h]
0x1800250fe  add     rsp, 28h
0x180025102  retn
0x180025103  mov     rax, [rcx]
0x180025106  mov     rax, [rax+rbx*8+180160h]
0x18002510e  test    rax, rax
0x180025111  jz      short loc_1800250B7
0x180025113  jmp     short loc_1800250C2
0x180025115  call    cs:__imp_GetThreadDpiAwarenessContext
0x18002511b  mov     rbx, rax
0x18002511e  shr     ebx, 8
0x180025121  and     ebx, 1FFh
0x180025127  call    cs:__imp_GetDpiForSession
0x18002512d  mov     edx, eax
0x18002512f  mov     ecx, ebx
0x180025131  call    GetDpiDepStockObjectPlateauSlot
0x180025136  cmp     eax, 0FFFFFFFFh
0x180025139  jz      short loc_18002516C
0x18002513b  cmp     eax, 0FFFFFFFEh
0x18002513e  jnz     short loc_18002515B
0x180025140  mov     rax, cs:__imp_pGdiSharedMemory
0x180025147  mov     rbx, [rsp+28h+arg_0]
0x18002514c  mov     rcx, [rax]
0x18002514f  mov     rax, [rcx+180138h]
0x180025156  add     rsp, 28h
0x18002515a  retn
0x18002515b  test    eax, eax
0x18002515d  jns     short loc_180025187
0x18002515f  mov     ecx, 57h ; 'W'
0x180025164  call    cs:__imp_GdiSetLastError
0x18002516a  jmp     short loc_180025140
0x18002516c  mov     rax, cs:__imp_pGdiSharedMemory
0x180025173  mov     rbx, [rsp+28h+arg_0]
0x180025178  mov     rcx, [rax]
0x18002517b  mov     rax, [rcx+1801E8h]
0x180025182  add     rsp, 28h
0x180025186  retn
0x180025187  mov     rcx, cs:__imp_pGdiSharedMemory
0x18002518e  cdqe
0x180025190  mov     [rsp+28h+var_8], rdi
0x180025195  lea     rdi, ds:180210h[rax*8]
0x18002519d  mov     rax, [rcx]
0x1800251a0  cmp     qword ptr [rdi+rax], 0
0x1800251a5  jnz     short loc_1800251B6
0x1800251a7  mov     ecx, ebx
0x1800251a9  call    cs:__imp_NtGdiEnsureDpiDepDefaultGuiFontForPlateau
0x1800251af  mov     rcx, cs:__imp_pGdiSharedMemory
0x1800251b6  mov     rax, [rcx]
0x1800251b9  mov     rax, [rdi+rax]
0x1800251bd  mov     rdi, [rsp+28h+var_8]
0x1800251c2  jmp     loc_1800250C2
```
