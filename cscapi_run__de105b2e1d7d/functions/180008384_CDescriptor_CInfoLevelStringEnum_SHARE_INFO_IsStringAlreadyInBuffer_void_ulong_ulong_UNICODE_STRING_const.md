# CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::IsStringAlreadyInBuffer(void *,ulong,ulong,_UNICODE_STRING const *)

- ea: `0x180008384`
- end: `0x180008417`
- name: `?IsStringAlreadyInBuffer@?$CDescriptor@VCInfoLevelStringEnum_SHARE_INFO@@@@QEAAEPEAXKKPEBU_UNICODE_STRING@@@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800016b0`

## callees

- `0x180008384`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800083e8`
- `msvcrt!_wcsnicmp` at `0x1800083e8`

## pseudocode

```c
char __fastcall CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::IsStringAlreadyInBuffer(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        const wchar_t **a5)
{
  char v8; // di
  unsigned int v9; // ebx
  size_t v10; // rbp
  const wchar_t **v11; // rsi
  const wchar_t *v12; // rsi

  v8 = 0;
  v9 = 0;
  v10 = (unsigned __int64)*(unsigned __int16 *)a5 >> 1;
  while ( v9 < a3 )
  {
    if ( *(_DWORD *)(a1 + 20) != -1 )
    {
      v11 = (const wchar_t **)(a2 + *(_DWORD *)(a1 + 68) * v9 + *(unsigned int *)(a1 + 20));
      if ( v11 )
      {
        v12 = *v11;
        if ( v12 )
        {
          if ( !_wcsnicmp(v12, a5[1], v10) && !v12[v10] )
            return 1;
        }
      }
    }
    ++v9;
  }
  return v8;
}

```

## disassembly

```asm
0x180008384  push    rbx
0x180008386  push    rbp
0x180008387  push    rsi
0x180008388  push    rdi
0x180008389  push    r12
0x18000838b  push    r13
0x18000838d  push    r14
0x18000838f  push    r15
0x180008391  sub     rsp, 28h
0x180008395  mov     r13, [rsp+68h+arg_20]
0x18000839d  mov     r15d, r8d
0x1800083a0  xor     r8d, r8d
0x1800083a3  mov     r12, rdx
0x1800083a6  mov     r14, rcx
0x1800083a9  mov     dil, r8b
0x1800083ac  mov     ebx, r8d
0x1800083af  movzx   ebp, word ptr [r13+0]
0x1800083b4  shr     rbp, 1
0x1800083b7  cmp     ebx, r15d
0x1800083ba  jnb     short loc_180008403
0x1800083bc  cmp     dword ptr [r14+14h], 0FFFFFFFFh
0x1800083c1  jz      short loc_1800083FC
0x1800083c3  mov     esi, [r14+14h]
0x1800083c7  mov     eax, ebx
0x1800083c9  imul    eax, [r14+44h]
0x1800083ce  add     rax, r12
0x1800083d1  add     rsi, rax
0x1800083d4  jz      short loc_1800083FC
0x1800083d6  mov     rsi, [rsi]
0x1800083d9  test    rsi, rsi
0x1800083dc  jz      short loc_1800083FC
0x1800083de  mov     rdx, [r13+8]; String2
0x1800083e2  mov     r8, rbp; MaxCount
0x1800083e5  mov     rcx, rsi; String1
0x1800083e8  call    cs:__imp__wcsnicmp
0x1800083ee  xor     r8d, r8d
0x1800083f1  test    eax, eax
0x1800083f3  jnz     short loc_1800083FC
0x1800083f5  cmp     [rsi+rbp*2], r8w
0x1800083fa  jz      short loc_180008400
0x1800083fc  inc     ebx
0x1800083fe  jmp     short loc_1800083B7
0x180008400  mov     dil, 1
0x180008403  mov     al, dil
0x180008406  add     rsp, 28h
0x18000840a  pop     r15
0x18000840c  pop     r14
0x18000840e  pop     r13
0x180008410  pop     r12
0x180008412  pop     rdi
0x180008413  pop     rsi
0x180008414  pop     rbp
0x180008415  pop     rbx
0x180008416  retn
```
