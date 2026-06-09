# PcQoSPUpdateFlow

- ea: `0x14000c5c0`
- end: `0x14000c6ae`
- name: `PcQoSPUpdateFlow`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, installer_update`

## callees

- `0x140003ab0`
- `0x14000c164`
- `0x14000c5c0`
- `0x14000c75c`

## pseudocode

```c
__int64 __fastcall PcQoSPUpdateFlow(__int64 *a1)
{
  __int64 v2; // rcx
  ULONG v3; // r8d
  unsigned int updated; // edi
  KAFFINITY v5; // rbx
  void *Src; // [rsp+20h] [rbp-48h]
  __int64 v8; // [rsp+28h] [rbp-40h]
  __int64 v9; // [rsp+30h] [rbp-38h]
  __int64 v10; // [rsp+40h] [rbp-28h]
  __int64 v11; // [rsp+70h] [rbp+8h] BYREF
  __int64 v12; // [rsp+78h] [rbp+10h] BYREF
  __int64 v13; // [rsp+80h] [rbp+18h] BYREF

  LODWORD(v13) = 0;
  v2 = *a1;
  LOWORD(v12) = 0;
  LOWORD(v11) = 0;
  v3 = *(_DWORD *)(v2 + 64) + 80;
  if ( *(_DWORD *)(v2 + 64) >= 0xFFFFFFB0 )
  {
    updated = -1073741675;
  }
  else if ( a1[1] >= (unsigned __int64)v3 )
  {
    v5 = a1[3];
    updated = PcpUpdateFlow(
                v5,
                0,
                v3,
                (unsigned __int8)*(_DWORD *)(v5 + 48),
                (char *)v2,
                *((_BYTE *)a1 + 16),
                *((_DWORD *)a1 + 8),
                &v13,
                &v12,
                &v11);
    LODWORD(v10) = v13;
    LODWORD(v9) = *(_DWORD *)(*a1 + 64);
    LOWORD(v8) = v11;
    LOWORD(Src) = v12;
    PcpTraceUpdateFlowEvent(
      v5,
      updated,
      (unsigned __int8)*(_DWORD *)(v5 + 48),
      *a1,
      Src,
      v8,
      v9,
      *(_QWORD *)(*a1 + 72),
      v10);
  }
  else
  {
    updated = -1073741789;
  }
  return PcpNormalizeNtStatus(updated);
}

```

## disassembly

```asm
0x14000c5c0  mov     rax, rsp
0x14000c5c3  push    rbx
0x14000c5c4  push    rsi
0x14000c5c5  push    rdi
0x14000c5c6  sub     rsp, 50h
0x14000c5ca  mov     dword ptr [rax+18h], 0
0x14000c5d1  mov     rsi, rcx
0x14000c5d4  mov     rcx, [rcx]
0x14000c5d7  xor     eax, eax
0x14000c5d9  mov     word ptr [rsp+68h+arg_8], ax
0x14000c5de  mov     word ptr [rsp+68h+arg_0], ax
0x14000c5e3  mov     r8d, [rcx+40h]
0x14000c5e7  add     r8d, 50h ; 'P'; int
0x14000c5eb  cmp     r8d, 50h ; 'P'
0x14000c5ef  jb      loc_14000C699
0x14000c5f5  mov     eax, r8d
0x14000c5f8  cmp     [rsi+8], rax
0x14000c5fc  jnb     short loc_14000C608
0x14000c5fe  mov     edi, 0C0000023h
0x14000c603  jmp     loc_14000C69E
0x14000c608  mov     rbx, [rsi+18h]
0x14000c60c  xor     edx, edx; int
0x14000c60e  mov     eax, [rbx+30h]
0x14000c611  movzx   r9d, al; int
0x14000c615  lea     rax, [rsp+68h+arg_0]
0x14000c61a  mov     [rsp+68h+var_20], rax; __int64
0x14000c61f  lea     rax, [rsp+68h+arg_8]
0x14000c624  mov     [rsp+68h+var_28], rax; __int64
0x14000c629  lea     rax, [rsp+68h+arg_10]
0x14000c631  mov     [rsp+68h+var_30], rax; __int64
0x14000c636  mov     eax, [rsi+20h]
0x14000c639  mov     dword ptr [rsp+68h+var_38], eax; int
0x14000c63d  mov     al, [rsi+10h]
0x14000c640  mov     [rsp+68h+var_40], al; char
0x14000c644  mov     [rsp+68h+Src], rcx; Src
0x14000c649  mov     rcx, rbx; int
0x14000c64c  call    PcpUpdateFlow
0x14000c651  mov     edx, [rbx+30h]
0x14000c654  mov     rcx, rbx
0x14000c657  mov     r9, [rsi]
0x14000c65a  mov     edi, eax
0x14000c65c  movzx   r8d, dl
0x14000c660  mov     edx, dword ptr [rsp+68h+arg_10]
0x14000c667  mov     dword ptr [rsp+68h+var_28], edx
0x14000c66b  mov     rdx, [r9+48h]
0x14000c66f  mov     [rsp+68h+var_30], rdx
0x14000c674  mov     edx, [r9+40h]
0x14000c678  mov     dword ptr [rsp+68h+var_38], edx
0x14000c67c  movzx   edx, word ptr [rsp+68h+arg_0]
0x14000c681  mov     word ptr [rsp+68h+var_40], dx
0x14000c686  movzx   edx, word ptr [rsp+68h+arg_8]
0x14000c68b  mov     word ptr [rsp+68h+Src], dx
0x14000c690  mov     edx, eax
0x14000c692  call    PcpTraceUpdateFlowEvent
0x14000c697  jmp     short loc_14000C69E
0x14000c699  mov     edi, 0C0000095h
0x14000c69e  mov     ecx, edi
0x14000c6a0  call    PcpNormalizeNtStatus
0x14000c6a5  add     rsp, 50h
0x14000c6a9  pop     rdi
0x14000c6aa  pop     rsi
0x14000c6ab  pop     rbx
0x14000c6ac  retn
```
