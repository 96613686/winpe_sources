# MakeFullSystemPath(ushort const *,ushort *,unsigned __int64)

- ea: `0x14000953c`
- end: `0x1400095dc`
- name: `?MakeFullSystemPath@@YA_NPEBGPEAG_K@Z`
- size: `160`
- prototype: `bool __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1400094c4`

## callees

- `0x1400086f8`
- `0x14000953c`
- `0x1400095e4`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x14000955c`
- `KERNEL32!lstrlenW` at `0x14000955c`

## pseudocode

```c
bool __fastcall MakeFullSystemPath(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int SystemDirectory; // eax
  bool result; // al

  result = (!a1 || !*a1 || lstrlenW(a1) < 2 || *a1 >= 0x7Fu || a1[1] != 58 && (*a1 != 92 || a1[1] != 92))
        && (SystemDirectory = MsiGetSystemDirectory(a2)) != 0
        && SystemDirectory + 2 <= 0x105
        && (a2[SystemDirectory] = 92, a2[SystemDirectory + 1] = 0, StringCchCatW(a2, 0x105u, a1) >= 0)
        && StringCchCatW(a2, 0x105u, L".DLL") >= 0;
  return result;
}

```

## disassembly

```asm
0x14000953c  push    rbx
0x14000953e  push    rbp
0x14000953f  push    rsi
0x140009540  push    rdi
0x140009541  sub     rsp, 28h
0x140009545  xor     esi, esi
0x140009547  mov     rdi, rdx
0x14000954a  mov     rbx, rcx
0x14000954d  mov     ebp, 5Ch ; '\'
0x140009552  test    rcx, rcx
0x140009555  jz      short loc_14000957F
0x140009557  cmp     [rcx], si
0x14000955a  jz      short loc_14000957F
0x14000955c  call    cs:__imp_lstrlenW
0x140009562  cmp     eax, 2
0x140009565  jl      short loc_14000957F
0x140009567  cmp     word ptr [rbx], 7Fh
0x14000956b  jnb     short loc_14000957F
0x14000956d  cmp     word ptr [rbx+2], 3Ah ; ':'
0x140009572  jz      short loc_1400095D1
0x140009574  cmp     [rbx], bp
0x140009577  jnz     short loc_14000957F
0x140009579  cmp     [rbx+2], bp
0x14000957d  jz      short loc_1400095D1
0x14000957f  mov     rcx, rdi; unsigned __int16 *
0x140009582  call    ?MsiGetSystemDirectory@@YAIPEAGIH@Z; MsiGetSystemDirectory(ushort *,uint,int)
0x140009587  test    eax, eax
0x140009589  jz      short loc_1400095D1
0x14000958b  lea     ecx, [rax+2]
0x14000958e  cmp     ecx, 105h
0x140009594  ja      short loc_1400095D1
0x140009596  mov     ecx, eax
0x140009598  mov     r8, rbx; unsigned __int16 *
0x14000959b  inc     eax
0x14000959d  mov     edx, 105h; unsigned __int64
0x1400095a2  mov     [rdi+rcx*2], bp
0x1400095a6  mov     rcx, rdi; unsigned __int16 *
0x1400095a9  mov     [rdi+rax*2], si
0x1400095ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400095b2  test    eax, eax
0x1400095b4  js      short loc_1400095D1
0x1400095b6  lea     r8, aDll; ".DLL"
0x1400095bd  mov     edx, 105h; unsigned __int64
0x1400095c2  mov     rcx, rdi; unsigned __int16 *
0x1400095c5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400095ca  shr     eax, 1Fh
0x1400095cd  xor     al, 1
0x1400095cf  jmp     short loc_1400095D3
0x1400095d1  xor     al, al
0x1400095d3  add     rsp, 28h
0x1400095d7  pop     rdi
0x1400095d8  pop     rsi
0x1400095d9  pop     rbp
0x1400095da  pop     rbx
0x1400095db  retn
```
