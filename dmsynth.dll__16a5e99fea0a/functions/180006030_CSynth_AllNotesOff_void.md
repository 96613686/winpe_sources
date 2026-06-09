# CSynth::AllNotesOff(void)

- ea: `0x180006030`
- end: `0x1800060c2`
- name: `?AllNotesOff@CSynth@@QEAAJXZ`
- size: `146`
- prototype: `__int64 __fastcall(CSynth *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800061a0`
- `0x180006ec0`
- `0x1800074b0`
- `0x18000e5c0`
- `0x1800115a0`

## callees

- `0x180006030`
- `0x18000b0f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006043`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006043`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800060b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800060b1`

## pseudocode

```c
__int64 __fastcall CSynth::AllNotesOff(CSynth *this)
{
  __int64 v2; // rbx
  CVoice *v3; // rcx
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  int v7; // r9d
  int v8; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  while ( 1 )
  {
    v2 = *((_QWORD *)this + 8);
    if ( !v2 )
      break;
    v3 = (CVoice *)*((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = *(_QWORD *)v2;
    *(_QWORD *)v2 = 0;
    CVoice::ClearVoice(v3);
    *(_DWORD *)(v2 + 544) = 0;
    *(_QWORD *)v2 = *((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = v2;
    v4 = *(_DWORD *)(v2 + 528);
    v5 = *(_QWORD *)(v2 + 520);
    v6 = *((_QWORD *)this + 10);
    v7 = v4 - v5;
    v8 = v4 - v6;
    if ( v5 < v6 )
      v7 = v8;
    *((_DWORD *)this + 23) += v7;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  return 0;
}

```

## disassembly

```asm
0x180006030  push    rbx
0x180006032  push    rbp
0x180006033  push    rsi
0x180006034  push    rdi
0x180006035  sub     rsp, 28h
0x180006039  mov     rdi, rcx
0x18000603c  add     rcx, 418h; lpCriticalSection
0x180006043  call    cs:__imp_EnterCriticalSection
0x180006049  xor     ebp, ebp
0x18000604b  nop     dword ptr [rax+rax+00h]
0x180006050  mov     rbx, [rdi+40h]
0x180006054  test    rbx, rbx
0x180006057  jz      short loc_1800060AA
0x180006059  mov     rax, [rbx]
0x18000605c  mov     rcx, rbx; this
0x18000605f  mov     [rdi+40h], rax
0x180006063  mov     [rbx], rbp
0x180006066  call    ?ClearVoice@CVoice@@QEAAXXZ; CVoice::ClearVoice(void)
0x18000606b  mov     [rbx+220h], ebp
0x180006071  mov     rax, [rdi+30h]
0x180006075  mov     [rbx], rax
0x180006078  mov     [rdi+30h], rbx
0x18000607c  mov     r9d, [rbx+210h]
0x180006083  mov     eax, r9d
0x180006086  mov     rcx, [rbx+208h]
0x18000608d  mov     r8, [rdi+50h]
0x180006091  sub     r9d, ecx
0x180006094  mov     edx, [rdi+5Ch]
0x180006097  sub     eax, r8d
0x18000609a  cmp     rcx, r8
0x18000609d  cmovl   r9d, eax
0x1800060a1  lea     eax, [rdx+r9]
0x1800060a5  mov     [rdi+5Ch], eax
0x1800060a8  jmp     short loc_180006050
0x1800060aa  lea     rcx, [rdi+418h]; lpCriticalSection
0x1800060b1  call    cs:__imp_LeaveCriticalSection
0x1800060b7  xor     eax, eax
0x1800060b9  add     rsp, 28h
0x1800060bd  pop     rdi
0x1800060be  pop     rsi
0x1800060bf  pop     rbp
0x1800060c0  pop     rbx
0x1800060c1  retn
```
