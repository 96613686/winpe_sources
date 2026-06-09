# DDIContextST::DDIContextST(CContext *,EErrorBehavior)

- ea: `0x180008ae0`
- end: `0x180008b56`
- name: `??0DDIContextST@@QEAA@PEAVCContext@@W4EErrorBehavior@@@Z`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `161`
- callee_count: `0`
- tags: ``

## callers

- `0x180001700`
- `0x1800035b4`
- `0x180006680`
- `0x180006f28`
- `0x1800072cc`
- `0x180007be0`
- `0x180007f7c`
- `0x1800081b0`
- `0x180008380`
- `0x1800084f0`
- `0x18000887c`
- `0x180008be8`
- `0x180009a64`
- `0x18000a03c`
- `0x18000a2d4`
- `0x18000a5e0`
- `0x180015a50`
- `0x180016010`
- `0x18003ad80`
- `0x18003baa0`
- `0x18004f538`
- `0x180050910`
- `0x180059820`
- `0x18005dbe0`
- `0x18005eecc`
- `0x18005fb84`
- `0x180061270`
- `0x180061470`
- `0x180061f60`
- `0x180062440`
- `0x1800626c0`
- `0x180062960`
- `0x180062aa0`
- `0x180063234`
- `0x1800633d0`
- `0x1800636e0`
- `0x180063930`
- `0x180063b70`
- `0x180063d80`
- `0x180063eb0`
- `0x18006430c`
- `0x1800654ec`
- `0x1800659cc`
- `0x180066e1c`
- `0x18006f3e4`
- `0x18007425c`
- `0x180074ed8`
- `0x1800790c0`
- `0x18007a550`
- `0x18007a7b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b10`

## pseudocode

```c
__int64 __fastcall DDIContextST::DDIContextST(__int64 a1, __int64 a2, char a3)
{
  __int64 result; // rax
  __int16 v7; // [rsp+31h] [rbp+9h]
  char v8; // [rsp+33h] [rbp+Bh]

  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 3688);
  *(_QWORD *)(a1 + 12) = *(_QWORD *)(a2 + 3692);
  *(_DWORD *)(a2 + 3688) = GetCurrentThreadId();
  *(_WORD *)(a2 + 3693) = v7;
  *(_BYTE *)(a2 + 3695) = v8;
  result = a1;
  *(_BYTE *)(a2 + 3692) = a3;
  *(_DWORD *)(a2 + 3696) = 0;
  return result;
}

```

## disassembly

```asm
0x180008ae0  mov     [rsp+arg_8], rbx
0x180008ae5  mov     [rsp+arg_10], rsi
0x180008aea  push    rdi
0x180008aeb  sub     rsp, 20h
0x180008aef  mov     [rcx], rdx
0x180008af2  movzx   ebx, r8b
0x180008af6  mov     eax, [rdx+0E68h]
0x180008afc  mov     rdi, rdx
0x180008aff  mov     [rcx+8], eax
0x180008b02  mov     rsi, rcx
0x180008b05  mov     rax, [rdx+0E6Ch]
0x180008b0c  mov     [rcx+0Ch], rax
0x180008b10  call    cs:__imp_GetCurrentThreadId
0x180008b16  mov     [rdi+0E68h], eax
0x180008b1c  movzx   eax, [rsp+28h+arg_1]
0x180008b21  mov     [rdi+0E6Dh], ax
0x180008b28  movzx   eax, [rsp+28h+arg_3]
0x180008b2d  mov     [rdi+0E6Fh], al
0x180008b33  mov     rax, rsi
0x180008b36  mov     rsi, [rsp+28h+arg_10]
0x180008b3b  mov     [rdi+0E6Ch], bl
0x180008b41  mov     rbx, [rsp+28h+arg_8]
0x180008b46  mov     dword ptr [rdi+0E70h], 0
0x180008b50  add     rsp, 20h
0x180008b54  pop     rdi
0x180008b55  retn
```
