# CopySTATPROPSTG(ulong,tagSTATPROPSTG *,tagSTATPROPSTG const *)

- ea: `0x180023ee0`
- end: `0x180023f6e`
- name: `?CopySTATPROPSTG@@YAJKPEAUtagSTATPROPSTG@@PEBU1@@Z`
- size: `142`
- prototype: `int(unsigned int, struct tagSTATPROPSTG *, const struct tagSTATPROPSTG *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023d90`
- `0x180023e8c`

## callees

- `0x18001e2f0`
- `0x180023ee0`
- `0x180043100`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023f33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023f33`

## pseudocode

```c
__int64 __fastcall CopySTATPROPSTG(unsigned int a1, struct tagSTATPROPSTG *a2, const struct tagSTATPROPSTG *a3)
{
  unsigned int v4; // esi
  struct tagSTATPROPSTG *v5; // rdi
  __int64 v6; // rax
  SIZE_T v7; // rbp
  unsigned __int16 *v8; // rax

  v4 = a1;
  v5 = a2;
  memset_0(a2, 0, 16LL * a1);
  while ( 1 )
  {
    if ( !v4 )
      return 0;
    *v5 = *a3;
    if ( a3->lpwstrName )
      break;
LABEL_8:
    --v4;
    ++v5;
    ++a3;
  }
  v6 = -1;
  do
    ++v6;
  while ( a3->lpwstrName[v6] );
  v7 = (unsigned int)(2 * v6 + 2);
  v8 = (unsigned __int16 *)CoTaskMemAlloc(v7);
  v5->lpwstrName = v8;
  if ( v8 )
  {
    StringCbCopyW(v8, (unsigned int)v7, a3->lpwstrName);
    goto LABEL_8;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x180023ee0  push    rbx
0x180023ee2  push    rbp
0x180023ee3  push    rsi
0x180023ee4  push    rdi
0x180023ee5  push    r14
0x180023ee7  sub     rsp, 20h
0x180023eeb  mov     rbx, r8
0x180023eee  mov     esi, ecx
0x180023ef0  mov     r8d, ecx
0x180023ef3  mov     rdi, rdx
0x180023ef6  shl     r8, 4; Size
0x180023efa  xor     edx, edx; Val
0x180023efc  mov     rcx, rdi; void *
0x180023eff  call    memset_0
0x180023f04  xor     r14d, r14d
0x180023f07  test    esi, esi
0x180023f09  jz      short loc_180023F5A
0x180023f0b  movups  xmm0, xmmword ptr [rbx]
0x180023f0e  movdqu  xmmword ptr [rdi], xmm0
0x180023f12  mov     rcx, [rbx]
0x180023f15  test    rcx, rcx
0x180023f18  jz      short loc_180023F4E
0x180023f1a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023f1e  inc     rax
0x180023f21  cmp     [rcx+rax*2], r14w
0x180023f26  jnz     short loc_180023F1E
0x180023f28  lea     eax, ds:2[rax*2]
0x180023f2f  mov     ecx, eax; cb
0x180023f31  mov     ebp, eax
0x180023f33  call    cs:__imp_CoTaskMemAlloc
0x180023f39  mov     [rdi], rax
0x180023f3c  test    rax, rax
0x180023f3f  jz      short loc_180023F67
0x180023f41  mov     r8, [rbx]; unsigned __int16 *
0x180023f44  mov     edx, ebp; unsigned __int64
0x180023f46  mov     rcx, rax; unsigned __int16 *
0x180023f49  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180023f4e  dec     esi
0x180023f50  add     rdi, 10h
0x180023f54  add     rbx, 10h
0x180023f58  jmp     short loc_180023F07
0x180023f5a  xor     eax, eax
0x180023f5c  add     rsp, 20h
0x180023f60  pop     r14
0x180023f62  pop     rdi
0x180023f63  pop     rsi
0x180023f64  pop     rbp
0x180023f65  pop     rbx
0x180023f66  retn
0x180023f67  mov     eax, 0C000009Ah
0x180023f6c  jmp     short loc_180023F5C
```
