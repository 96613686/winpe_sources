# AppendExtension(ushort const *,ushort const *,CAPITempBufferRef<ushort> &)

- ea: `0x140003ffc`
- end: `0x1400040cb`
- name: `?AppendExtension@@YA?AW4Bool@@PEBG0AEAV?$CAPITempBufferRef@G@@@Z`
- size: `207`
- prototype: `_BOOL8 __fastcall(unsigned __int16 *, __int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x140003ea0`
- `0x140004ca8`
- `0x140006e10`

## callees

- `0x140003c8c`
- `0x140003ffc`
- `0x1400081f0`
- `0x1400086f8`
- `0x1400087bc`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x14000406a`
- `KERNEL32!lstrlenW` at `0x140004079`
- `KERNEL32!lstrlenW` at `0x14000406a`
- `KERNEL32!lstrlenW` at `0x140004079`

## pseudocode

```c
_BOOL8 __fastcall AppendExtension(unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  const WCHAR *v4; // rdi
  unsigned __int16 v5; // ax
  const unsigned __int16 *v6; // r9
  unsigned __int16 *v7; // rax
  unsigned __int16 i; // ax
  int v9; // ebx
  int v10; // eax

  v4 = a1;
  if ( !a1 )
    return 0;
  v5 = *a1;
  v6 = a1;
  if ( *a1 )
  {
    do
    {
      if ( v5 == 92 )
      {
        v7 = (unsigned __int16 *)APICharNext(a1);
        v6 = v7;
      }
      else
      {
        v7 = (unsigned __int16 *)APICharNext(a1);
      }
      a1 = v7;
      v5 = *v7;
    }
    while ( v5 );
    for ( i = *v6; i && i != 46; i = *v6 )
      v6 = APICharNext(v6);
  }
  if ( *v6 == 46 )
    return 0;
  v9 = lstrlenW(v4);
  v10 = lstrlenW(L".msi");
  CAPITempBufferRef<unsigned short>::SetSize(a3, (unsigned int)(v9 + v10 + 1), 0);
  return !StringCchCopyW(*(unsigned __int16 **)a3, *(int *)(a3 + 8), v4)
      && StringCchCatW(*(unsigned __int16 **)a3, *(int *)(a3 + 8), L".msi") == 0;
}

```

## disassembly

```asm
0x140003ffc  push    rbx
0x140003ffe  push    rbp
0x140003fff  push    rsi
0x140004000  push    rdi
0x140004001  sub     rsp, 28h
0x140004005  xor     ebp, ebp
0x140004007  mov     rsi, r8
0x14000400a  mov     rdi, rcx
0x14000400d  test    rcx, rcx
0x140004010  jz      loc_1400040C0
0x140004016  movzx   eax, word ptr [rcx]
0x140004019  mov     r9, rcx
0x14000401c  test    ax, ax
0x14000401f  jz      short loc_140004060
0x140004021  cmp     ax, 5Ch ; '\'
0x140004025  jnz     short loc_140004031
0x140004027  call    ?APICharNext@@YAPEBGPEBG@Z; APICharNext(ushort const *)
0x14000402c  mov     r9, rax
0x14000402f  jmp     short loc_140004036
0x140004031  call    ?APICharNext@@YAPEBGPEBG@Z; APICharNext(ushort const *)
0x140004036  mov     rcx, rax
0x140004039  movzx   eax, word ptr [rax]
0x14000403c  test    ax, ax
0x14000403f  jnz     short loc_140004021
0x140004041  movzx   eax, word ptr [r9]
0x140004045  jmp     short loc_14000405B
0x140004047  cmp     ax, 2Eh ; '.'
0x14000404b  jz      short loc_140004060
0x14000404d  mov     rcx, r9; unsigned __int16 *
0x140004050  call    ?APICharNext@@YAPEBGPEBG@Z; APICharNext(ushort const *)
0x140004055  mov     r9, rax
0x140004058  movzx   eax, word ptr [rax]
0x14000405b  test    ax, ax
0x14000405e  jnz     short loc_140004047
0x140004060  cmp     word ptr [r9], 2Eh ; '.'
0x140004065  jz      short loc_1400040C0
0x140004067  mov     rcx, rdi; lpString
0x14000406a  call    cs:__imp_lstrlenW
0x140004070  lea     rcx, String; ".msi"
0x140004077  mov     ebx, eax
0x140004079  call    cs:__imp_lstrlenW
0x14000407f  xor     r8d, r8d
0x140004082  mov     rcx, rsi
0x140004085  lea     edx, [rax+1]
0x140004088  add     edx, ebx
0x14000408a  call    ?SetSize@?$CAPITempBufferRef@G@@QEAA_NH_N@Z; CAPITempBufferRef<ushort>::SetSize(int,bool)
0x14000408f  movsxd  rdx, dword ptr [rsi+8]; unsigned __int64
0x140004093  mov     r8, rdi; unsigned __int16 *
0x140004096  mov     rcx, [rsi]; unsigned __int16 *
0x140004099  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000409e  test    eax, eax
0x1400040a0  jnz     short loc_1400040C0
0x1400040a2  movsxd  rdx, dword ptr [rsi+8]; unsigned __int64
0x1400040a6  lea     r8, String; ".msi"
0x1400040ad  mov     rcx, [rsi]; unsigned __int16 *
0x1400040b0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400040b5  test    eax, eax
0x1400040b7  mov     ecx, ebp
0x1400040b9  setz    cl
0x1400040bc  mov     eax, ecx
0x1400040be  jmp     short loc_1400040C2
0x1400040c0  xor     eax, eax
0x1400040c2  add     rsp, 28h
0x1400040c6  pop     rdi
0x1400040c7  pop     rsi
0x1400040c8  pop     rbp
0x1400040c9  pop     rbx
0x1400040ca  retn
```
