# CSafeSem::Release(void)

- ea: `0x180016810`
- end: `0x180016902`
- name: `?Release@CSafeSem@@QEAAXXZ`
- size: `242`
- prototype: `void __fastcall(CSafeSem *__hidden this)`
- caller_count: `35`
- callee_count: `1`
- tags: ``

## callers

- `0x180006d80`
- `0x180007310`
- `0x18000a780`
- `0x18000aef0`
- `0x18000b680`
- `0x18000b904`
- `0x180010710`
- `0x180015280`
- `0x180015420`
- `0x180015880`
- `0x1800162a0`
- `0x18001c99c`
- `0x18001f0b0`
- `0x18001f1c4`
- `0x1800205e0`
- `0x1800216a0`
- `0x180021cf0`
- `0x180024020`
- `0x180032890`
- `0x180035890`
- `0x180037fa0`
- `0x180038970`
- `0x180039ca0`
- `0x18003abf0`
- `0x18003d780`
- `0x180041890`
- `0x18004b010`
- `0x18004b8d0`
- `0x18004bd30`
- `0x18004bfa0`
- `0x18004c130`
- `0x18004c5a0`
- `0x18004d610`
- `0x18004e400`
- `0x18004e480`

## callees

- `0x180016810`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001686c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001686c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800168fa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800168fa`

## pseudocode

```c
void __fastcall CSafeSem::Release(CSafeSem *this)
{
  __int64 v1; // rdx
  __int64 v3; // r8
  __int64 v4; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v6; // rcx
  bool v7; // zf
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // r9
  int v11; // ecx
  int v12; // eax

  v1 = *((_QWORD *)this + 3);
  if ( v1 )
  {
    v3 = *((_QWORD *)this + 2);
    if ( v3 )
    {
      v9 = *(_QWORD *)(v3 + 88);
      v10 = *(_QWORD *)(v3 + 96);
      v11 = *(_DWORD *)(v3 + 104);
      *(_QWORD *)(v1 + 8) = v9;
      *(_QWORD *)(v1 + 16) = v10;
      if ( v9 )
        v12 = *(_DWORD *)(v9 + 16) - 24;
      else
        v12 = 0;
      *(_DWORD *)(v1 + 32) = v12;
      *(_DWORD *)(v1 + 36) = v11;
      *(_QWORD *)NtCurrentTeb()->ReservedForOle = v10;
    }
    else
    {
      *(_QWORD *)(v1 + 8) = 0;
      v3 = 0;
      *(_QWORD *)(v1 + 16) = 0;
      *(_QWORD *)(v1 + 32) = 0;
      *(_QWORD *)NtCurrentTeb()->ReservedForOle = 0;
    }
    *(_QWORD *)(v1 + 24) = v3;
    *((_QWORD *)this + 3) = 0;
  }
  if ( *(int *)this >= 0 )
  {
    v4 = *((_QWORD *)this + 1);
    CurrentThreadId = GetCurrentThreadId();
    v6 = *(_QWORD *)(v4 + 112);
    if ( *(_DWORD *)(v6 + 8) == CurrentThreadId )
    {
      v7 = (*(_DWORD *)(v6 + 4))-- == 1;
      v8 = *(_QWORD *)(v4 + 112);
      if ( v7 )
      {
        *(_DWORD *)(v8 + 8) = 0;
        if ( _InterlockedDecrement(*(volatile signed __int32 **)(v4 + 112)) >= 0 )
          SetEvent(*(HANDLE *)(v4 + 120));
      }
      else
      {
        _InterlockedDecrement((volatile signed __int32 *)v8);
      }
    }
  }
  *(_DWORD *)this = -2147286784;
}

```

## disassembly

```asm
0x180016810  mov     [rsp+arg_10], rbx
0x180016815  push    rsi
0x180016816  sub     rsp, 20h
0x18001681a  mov     rdx, [rcx+18h]
0x18001681e  xor     esi, esi
0x180016820  mov     rbx, rcx
0x180016823  test    rdx, rdx
0x180016826  jz      short loc_18001685F
0x180016828  mov     r8, [rcx+10h]
0x18001682c  test    r8, r8
0x18001682f  jnz     loc_1800168B5
0x180016835  mov     [rdx+8], rsi
0x180016839  mov     r8d, esi
0x18001683c  mov     [rdx+10h], rsi
0x180016840  mov     [rdx+20h], rsi
0x180016844  mov     rax, gs:30h
0x18001684d  mov     rcx, [rax+1758h]
0x180016854  mov     [rcx], rsi
0x180016857  mov     [rdx+18h], r8
0x18001685b  mov     [rbx+18h], rsi
0x18001685f  cmp     [rbx], esi
0x180016861  jl      short loc_18001689F
0x180016863  mov     [rsp+28h+arg_8], rdi
0x180016868  mov     rdi, [rbx+8]
0x18001686c  call    cs:__imp_GetCurrentThreadId
0x180016872  mov     rcx, [rdi+70h]
0x180016876  cmp     [rcx+8], eax
0x180016879  jnz     short loc_18001689A
0x18001687b  sub     dword ptr [rcx+4], 1
0x18001687f  mov     rax, [rdi+70h]
0x180016883  jnz     short loc_1800168B0
0x180016885  mov     [rax+8], esi
0x180016888  mov     ecx, 0FFFFFFFFh
0x18001688d  mov     rax, [rdi+70h]
0x180016891  lock xadd [rax], ecx
0x180016895  cmp     ecx, 1
0x180016898  jns     short loc_1800168F6
0x18001689a  mov     rdi, [rsp+28h+arg_8]
0x18001689f  mov     dword ptr [rbx], 80030100h
0x1800168a5  mov     rbx, [rsp+28h+arg_10]
0x1800168aa  add     rsp, 20h
0x1800168ae  pop     rsi
0x1800168af  retn
0x1800168b0  lock dec dword ptr [rax]
0x1800168b3  jmp     short loc_18001689A
0x1800168b5  mov     rax, [r8+58h]
0x1800168b9  mov     r9, [r8+60h]
0x1800168bd  mov     ecx, [r8+68h]
0x1800168c1  mov     [rdx+8], rax
0x1800168c5  mov     [rdx+10h], r9
0x1800168c9  test    rax, rax
0x1800168cc  jz      short loc_1800168F2
0x1800168ce  mov     eax, [rax+10h]
0x1800168d1  sub     eax, 18h
0x1800168d4  mov     [rdx+20h], eax
0x1800168d7  mov     [rdx+24h], ecx
0x1800168da  mov     rax, gs:30h
0x1800168e3  mov     rcx, [rax+1758h]
0x1800168ea  mov     [rcx], r9
0x1800168ed  jmp     loc_180016857
0x1800168f2  mov     eax, esi
0x1800168f4  jmp     short loc_1800168D4
0x1800168f6  mov     rcx, [rdi+78h]; hEvent
0x1800168fa  call    cs:__imp_SetEvent
0x180016900  jmp     short loc_18001689A
```
