# EtwpDecompressBufferInPlace(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)

- ea: `0x18001526c`
- end: `0x18001531f`
- name: `?EtwpDecompressBufferInPlace@@YAKPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z`
- size: `179`
- prototype: `ULONG __fastcall(struct _TRACELOG_CONTEXT *, struct _WMI_BUFFER_HEADER *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014b10`
- `0x180015328`

## callees

- `0x180001ee2`
- `0x18001526c`
- `0x180015834`

## import_xrefs

- `ntdll!RtlDecompressBufferEx` at `0x1800152de`
- `ntdll!RtlDecompressBufferEx` at `0x1800152de`

## pseudocode

```c
ULONG __fastcall EtwpDecompressBufferInPlace(struct _TRACELOG_CONTEXT *a1, struct _WMI_BUFFER_HEADER *a2)
{
  bool v2; // zf
  void *v5; // rcx
  unsigned int v6; // ebp
  NTSTATUS v7; // eax
  ULONG result; // eax
  __int64 v9; // rdx
  unsigned int v10; // [rsp+78h] [rbp+10h] BYREF

  v2 = (*((_BYTE *)a2 + 52) & 0x40) == 0;
  v10 = 0;
  if ( !v2 )
  {
    v5 = (void *)*((_QWORD *)a1 + 81);
    v6 = *(_DWORD *)a2 - 72;
    if ( !v5 )
      return 1392;
    memcpy_0(v5, (char *)a2 + 72, v6);
    v7 = RtlDecompressBufferEx(
           *((unsigned __int16 *)a1 + 277),
           (char *)a2 + 72,
           (unsigned int)(*((_DWORD *)a2 + 12) - 72),
           *((_QWORD *)a1 + 81),
           v6,
           &v10,
           *((_QWORD *)a1 + 82));
    result = RtlNtStatusToDosError_0(v7);
    if ( result )
      return result;
    v9 = v10;
    *((_WORD *)a2 + 26) &= ~0x40u;
    if ( *((_DWORD *)a2 + 12) != v9 + 72 )
      return 1392;
    *(_DWORD *)a2 = v9 + 72;
  }
  return 0;
}

```

## disassembly

```asm
0x18001526c  push    rbx
0x18001526e  push    rbp
0x18001526f  push    rsi
0x180015270  push    rdi
0x180015271  sub     rsp, 48h
0x180015275  test    byte ptr [rdx+34h], 40h
0x180015279  mov     rdi, rdx
0x18001527c  mov     rsi, rcx
0x18001527f  mov     [rsp+68h+arg_8], 0
0x180015287  jz      loc_18001530D
0x18001528d  mov     ebp, [rdx]
0x18001528f  mov     rcx, [rcx+288h]; void *
0x180015296  add     ebp, 0FFFFFFB8h
0x180015299  test    rcx, rcx
0x18001529c  jz      short loc_180015318
0x18001529e  mov     r8d, ebp; Size
0x1800152a1  add     rdx, 48h ; 'H'; Src
0x1800152a5  call    memcpy_0
0x1800152aa  mov     rax, [rsi+290h]
0x1800152b1  lea     rdx, [rdi+48h]
0x1800152b5  mov     r8d, [rdi+30h]
0x1800152b9  mov     r9, [rsi+288h]
0x1800152c0  sub     r8d, 48h ; 'H'
0x1800152c4  movzx   ecx, word ptr [rsi+22Ah]
0x1800152cb  mov     [rsp+68h+var_38], rax
0x1800152d0  lea     rax, [rsp+68h+arg_8]
0x1800152d5  mov     [rsp+68h+var_40], rax
0x1800152da  mov     [rsp+68h+var_48], ebp
0x1800152de  call    cs:__imp_RtlDecompressBufferEx
0x1800152e4  mov     ecx, eax; Status
0x1800152e6  call    RtlNtStatusToDosError_0
0x1800152eb  test    eax, eax
0x1800152ed  jnz     short loc_18001530F
0x1800152ef  mov     edx, [rsp+68h+arg_8]
0x1800152f3  mov     eax, 0FFBFh
0x1800152f8  and     [rdi+34h], ax
0x1800152fc  mov     eax, [rdi+30h]
0x1800152ff  lea     rcx, [rdx+48h]
0x180015303  cmp     rax, rcx
0x180015306  jnz     short loc_180015318
0x180015308  lea     eax, [rdx+48h]
0x18001530b  mov     [rdi], eax
0x18001530d  xor     eax, eax
0x18001530f  add     rsp, 48h
0x180015313  pop     rdi
0x180015314  pop     rsi
0x180015315  pop     rbp
0x180015316  pop     rbx
0x180015317  retn
0x180015318  mov     eax, 570h
0x18001531d  jmp     short loc_18001530F
```
