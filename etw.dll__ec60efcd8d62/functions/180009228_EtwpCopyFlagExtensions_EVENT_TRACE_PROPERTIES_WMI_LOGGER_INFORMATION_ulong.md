# EtwpCopyFlagExtensions(_EVENT_TRACE_PROPERTIES *,_WMI_LOGGER_INFORMATION *,ulong)

- ea: `0x180009228`
- end: `0x180009300`
- name: `?EtwpCopyFlagExtensions@@YAKPEAU_EVENT_TRACE_PROPERTIES@@PEAU_WMI_LOGGER_INFORMATION@@K@Z`
- size: `216`
- prototype: `unsigned int __fastcall(struct _EVENT_TRACE_PROPERTIES *, struct _WMI_LOGGER_INFORMATION *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800099c0`
- `0x18000a300`
- `0x18000c4a0`
- `0x18000cca0`

## callees

- `0x180009228`
- `0x180015834`

## pseudocode

```c
__int64 __fastcall EtwpCopyFlagExtensions(
        struct _EVENT_TRACE_PROPERTIES *a1,
        struct _WMI_LOGGER_INFORMATION *a2,
        int a3)
{
  int v4; // edx
  unsigned int v5; // edx
  unsigned int v6; // r8d
  _WORD *v7; // r9
  size_t v8; // r8
  char *v9; // rdx
  void *v10; // rcx
  __int16 v11; // dx
  __int16 v12; // ax

  if ( *((int *)a2 + 18) < 0 )
  {
    if ( BYTE2(a1->EnableFlags) == 0xFF )
      v4 = *(unsigned __int16 *)((char *)&a1->Wnode.BufferSize + LOWORD(a1->EnableFlags));
    else
      v4 = BYTE2(a1->EnableFlags) + 2;
    v5 = 4 * v4;
    v6 = a3 - v5;
    *((_BYTE *)a2 + 74) = -1;
    *((_WORD *)a2 + 36) = v6;
    v7 = (_WORD *)((char *)a2 + v6);
    if ( BYTE2(a1->EnableFlags) == 0xFF )
    {
      v8 = v5;
      v9 = (char *)a1 + LOWORD(a1->EnableFlags);
      v10 = v7;
    }
    else
    {
      v11 = 1;
      v12 = BYTE2(a1->EnableFlags) + 2;
      v7[1] = 1;
      *v7 = v12;
      v7[2] = BYTE2(a1->EnableFlags) + 1;
      if ( (*(_QWORD *)&a1->Wnode.Guid.Data1 != *(_QWORD *)&SystemTraceControlGuid.Data1
         || *(_QWORD *)a1->Wnode.Guid.Data4 != *(_QWORD *)SystemTraceControlGuid.Data4)
        && *(_OWORD *)&a1->Wnode.Guid != CKCLGuid )
      {
        v11 = 2;
      }
      v7[3] = v11;
      v8 = 4LL * BYTE2(a1->EnableFlags);
      v9 = (char *)a1 + LOWORD(a1->EnableFlags);
      v10 = v7 + 4;
    }
    memcpy_0(v10, v9, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180009228  sub     rsp, 28h
0x18000922c  cmp     dword ptr [rdx+48h], 0
0x180009230  mov     r9, rdx
0x180009233  jge     loc_1800092F9
0x180009239  cmp     byte ptr [rcx+4Ah], 0FFh
0x18000923d  mov     r10d, 2
0x180009243  jnz     short loc_18000924F
0x180009245  movzx   eax, word ptr [rcx+48h]
0x180009249  movzx   edx, word ptr [rax+rcx]
0x18000924d  jmp     short loc_180009256
0x18000924f  movzx   edx, byte ptr [rcx+4Ah]
0x180009253  add     edx, r10d
0x180009256  shl     edx, 2
0x180009259  sub     r8d, edx
0x18000925c  mov     byte ptr [r9+4Ah], 0FFh
0x180009261  mov     eax, r8d
0x180009264  mov     [r9+48h], ax
0x180009269  add     r9, rax
0x18000926c  cmp     byte ptr [rcx+4Ah], 0FFh
0x180009270  jnz     short loc_180009281
0x180009272  mov     r8d, edx
0x180009275  movzx   edx, word ptr [rcx+48h]
0x180009279  add     rdx, rcx
0x18000927c  mov     rcx, r9
0x18000927f  jmp     short loc_1800092F4
0x180009281  movzx   eax, byte ptr [rcx+4Ah]
0x180009285  mov     edx, 1
0x18000928a  add     ax, r10w
0x18000928e  mov     [r9+2], dx
0x180009293  mov     [r9], ax
0x180009297  movzx   eax, byte ptr [rcx+4Ah]
0x18000929b  add     ax, dx
0x18000929e  mov     [r9+4], ax
0x1800092a3  mov     rax, [rcx+18h]
0x1800092a7  cmp     rax, qword ptr cs:SystemTraceControlGuid.Data1
0x1800092ae  jnz     short loc_1800092BD
0x1800092b0  mov     rax, [rcx+20h]
0x1800092b4  cmp     rax, qword ptr cs:SystemTraceControlGuid.Data4
0x1800092bb  jz      short loc_1800092DB
0x1800092bd  mov     rax, [rcx+18h]
0x1800092c1  cmp     rax, qword ptr cs:CKCLGuid
0x1800092c8  jnz     short loc_1800092D7
0x1800092ca  mov     rax, [rcx+20h]
0x1800092ce  cmp     rax, qword ptr cs:CKCLGuid+8
0x1800092d5  jz      short loc_1800092DB
0x1800092d7  movzx   edx, r10w
0x1800092db  mov     [r9+6], dx
0x1800092e0  movzx   r8d, byte ptr [rcx+4Ah]
0x1800092e5  movzx   edx, word ptr [rcx+48h]
0x1800092e9  shl     r8, 2; Size
0x1800092ed  add     rdx, rcx; Src
0x1800092f0  lea     rcx, [r9+8]; void *
0x1800092f4  call    memcpy_0
0x1800092f9  xor     eax, eax
0x1800092fb  add     rsp, 28h
0x1800092ff  retn
```
