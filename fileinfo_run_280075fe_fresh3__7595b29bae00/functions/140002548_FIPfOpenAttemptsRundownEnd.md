# FIPfOpenAttemptsRundownEnd

- ea: `0x140002548`
- end: `0x140002601`
- name: `FIPfOpenAttemptsRundownEnd`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001790`
- `0x140010cd0`

## callees

- `0x140002548`

## pseudocode

```c
__int64 __fastcall FIPfOpenAttemptsRundownEnd(__int64 a1)
{
  int *v1; // r9
  volatile signed __int32 *v2; // rcx
  volatile signed __int32 *v3; // rax
  __int64 result; // rax
  __int64 v5; // [rsp+8h] [rbp+8h]

  if ( a1 == 1 )
  {
    v3 = &dword_14000986C;
    v1 = &dword_140009550;
    v2 = &dword_14000956C;
  }
  else if ( a1 == 2 )
  {
    v3 = &dword_140009880;
    v1 = &dword_140009520;
    v2 = &dword_14000953C;
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 452));
    v1 = (int *)(a1 + 232);
    v2 = (volatile signed __int32 *)(a1 + 260);
    v3 = &dword_140009894;
  }
  _InterlockedIncrement(v3);
  result = (unsigned int)_InterlockedExchangeAdd(v2, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    HIDWORD(v5) = _InterlockedIncrement(&dword_140009640);
    LODWORD(v5) = ((MEMORY[0xFFFFF78000000004] * MEMORY[0xFFFFF78000000324]) << 8)
                + ((MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
    result = v5;
    *(_QWORD *)v1 = v5;
  }
  return result;
}

```

## disassembly

```asm
0x140002548  cmp     rcx, 1
0x14000254c  jz      loc_1400025E7
0x140002552  cmp     rcx, 2
0x140002556  jz      short loc_1400025D0
0x140002558  lock inc dword ptr [rcx+1C4h]
0x14000255f  lea     r9, [rcx+0E8h]
0x140002566  add     rcx, 104h
0x14000256d  lea     rax, dword_140009894
0x140002574  lock inc dword ptr [rax]
0x140002577  or      eax, 0FFFFFFFFh
0x14000257a  lock xadd [rcx], eax
0x14000257e  cmp     eax, 1
0x140002581  jnz     short locret_1400025CE
0x140002583  lock xadd cs:dword_140009640, eax
0x14000258b  inc     eax
0x14000258d  mov     rcx, 0FFFFF78000000320h
0x140002597  mov     dword ptr [rsp+arg_0+4], eax
0x14000259b  mov     rcx, [rcx]
0x14000259e  mov     eax, ds:0FFFFF78000000004h
0x1400025a7  mov     edx, ecx
0x1400025a9  mov     r8d, eax
0x1400025ac  shr     rcx, 20h
0x1400025b0  imul    ecx, eax
0x1400025b3  imul    r8, rdx
0x1400025b7  shl     ecx, 8
0x1400025ba  shr     r8, 18h
0x1400025be  add     r8d, ecx
0x1400025c1  mov     dword ptr [rsp+arg_0], r8d
0x1400025c6  mov     rax, [rsp+arg_0]
0x1400025cb  mov     [r9], rax
0x1400025ce  retn
0x1400025d0  lea     rax, dword_140009880
0x1400025d7  lea     r9, dword_140009520
0x1400025de  lea     rcx, dword_14000953C
0x1400025e5  jmp     short loc_140002574
0x1400025e7  lea     rax, dword_14000986C
0x1400025ee  lea     r9, dword_140009550
0x1400025f5  lea     rcx, dword_14000956C
0x1400025fc  jmp     loc_140002574
```
