# CounterHelper::DeleteCounter(int)

- ea: `0x180005be0`
- end: `0x180005cd9`
- name: `?DeleteCounter@CounterHelper@@QEAAXH@Z`
- size: `249`
- prototype: `void __fastcall(CounterHelper *__hidden this, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180005be0`
- `0x180007ecc`
- `0x180007f88`

## callees

- `0x1800058b8`
- `0x180005be0`
- `0x1800095e8`

## pseudocode

```c
void __fastcall CounterHelper::DeleteCounter(CounterHelper *this, int a2)
{
  int v2; // eax
  __int64 *v4; // rbx
  CounterHelper *ProcCounter; // rax
  __int64 *i; // rax
  __int64 *v7; // rcx
  unsigned int v8; // r9d
  __int64 v9; // rax
  __int64 v10; // rcx
  int v11; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    v2 = *((_DWORD *)this + 104);
    if ( v2 == 1 )
    {
      v4 = *(__int64 **)CounterHelper::ProcessesInSession;
      while ( 1 )
      {
        while ( 1 )
        {
          do
          {
            if ( v4 == (__int64 *)CounterHelper::ProcessesInSession )
              return;
            ProcCounter = CreateOrGetProcCounter(*((_DWORD *)v4 + 8));
            if ( ProcCounter )
              CounterHelper::DeleteCounter(ProcCounter, 0);
          }
          while ( *((_BYTE *)v4 + 25) );
          i = (__int64 *)v4[2];
          if ( !*((_BYTE *)i + 25) )
            break;
          for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v4 = i;
LABEL_16:
          v4 = i;
        }
        v7 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_16;
        do
        {
          v4 = v7;
          v7 = (__int64 *)*v7;
        }
        while ( !*((_BYTE *)v7 + 25) );
      }
    }
    if ( !v2 )
    {
      v8 = *((_DWORD *)this + 105);
      v9 = CounterHelper::SessionToCounter;
      v10 = *(_QWORD *)(CounterHelper::SessionToCounter + 8);
      while ( !*(_BYTE *)(v10 + 25) )
      {
        if ( *(_DWORD *)(v10 + 32) >= v8 )
        {
          v9 = v10;
          v10 = *(_QWORD *)v10;
        }
        else
        {
          v10 = *(_QWORD *)(v10 + 16);
        }
      }
      if ( v9 == CounterHelper::SessionToCounter || v8 < *(_DWORD *)(v9 + 32) )
        v9 = CounterHelper::SessionToCounter;
      if ( v9 != CounterHelper::SessionToCounter )
      {
        v11 = *((_DWORD *)this + 106);
        std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::erase(
          &CounterHelper::ProcessesInSession,
          &v11);
      }
    }
  }
}

```

## disassembly

```asm
0x180005be0  test    edx, edx
0x180005be2  jz      locret_180005CD8
0x180005be8  push    rbx
0x180005be9  sub     rsp, 20h
0x180005bed  mov     eax, [rcx+1A0h]
0x180005bf3  mov     r8, rcx
0x180005bf6  cmp     eax, 1
0x180005bf9  jnz     short loc_180005C71
0x180005bfb  mov     rbx, cs:?ProcessesInSession@CounterHelper@@0V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesInSession
0x180005c02  mov     rbx, [rbx]
0x180005c05  cmp     rbx, cs:?ProcessesInSession@CounterHelper@@0V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesInSession
0x180005c0c  jz      loc_180005CD3
0x180005c12  mov     ecx, [rbx+20h]; dwProcessId
0x180005c15  call    ?CreateOrGetProcCounter@@YAPEAVCounterHelper@@K@Z; CreateOrGetProcCounter(ulong)
0x180005c1a  test    rax, rax
0x180005c1d  jz      short loc_180005C29
0x180005c1f  xor     edx, edx; int
0x180005c21  mov     rcx, rax; this
0x180005c24  call    ?DeleteCounter@CounterHelper@@QEAAXH@Z; CounterHelper::DeleteCounter(int)
0x180005c29  cmp     byte ptr [rbx+19h], 0
0x180005c2d  jnz     short loc_180005C05
0x180005c2f  mov     rax, [rbx+10h]
0x180005c33  cmp     byte ptr [rax+19h], 0
0x180005c37  jnz     short loc_180005C53
0x180005c39  mov     rcx, [rax]
0x180005c3c  cmp     byte ptr [rcx+19h], 0
0x180005c40  jnz     short loc_180005C6C
0x180005c42  mov     rax, [rcx]
0x180005c45  mov     rbx, rcx
0x180005c48  mov     rcx, rax
0x180005c4b  cmp     byte ptr [rax+19h], 0
0x180005c4f  jz      short loc_180005C42
0x180005c51  jmp     short loc_180005C05
0x180005c53  mov     rax, [rbx+8]
0x180005c57  jmp     short loc_180005C66
0x180005c59  cmp     rbx, [rax+10h]
0x180005c5d  jnz     short loc_180005C6C
0x180005c5f  mov     rbx, rax
0x180005c62  mov     rax, [rax+8]
0x180005c66  cmp     byte ptr [rax+19h], 0
0x180005c6a  jz      short loc_180005C59
0x180005c6c  mov     rbx, rax
0x180005c6f  jmp     short loc_180005C05
0x180005c71  test    eax, eax
0x180005c73  jnz     short loc_180005CD3
0x180005c75  mov     rdx, cs:?SessionToCounter@CounterHelper@@2V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::SessionToCounter
0x180005c7c  mov     r9d, [rcx+1A4h]
0x180005c83  mov     rax, rdx
0x180005c86  mov     rcx, [rdx+8]
0x180005c8a  jmp     short loc_180005C9E
0x180005c8c  cmp     [rcx+20h], r9d
0x180005c90  jnb     short loc_180005C98
0x180005c92  mov     rcx, [rcx+10h]
0x180005c96  jmp     short loc_180005C9E
0x180005c98  mov     rax, rcx
0x180005c9b  mov     rcx, [rcx]
0x180005c9e  cmp     byte ptr [rcx+19h], 0
0x180005ca2  jz      short loc_180005C8C
0x180005ca4  cmp     rax, rdx
0x180005ca7  jz      short loc_180005CAF
0x180005ca9  cmp     r9d, [rax+20h]
0x180005cad  jnb     short loc_180005CB2
0x180005caf  mov     rax, rdx
0x180005cb2  cmp     rax, rdx
0x180005cb5  jz      short loc_180005CD3
0x180005cb7  mov     eax, [r8+1A8h]
0x180005cbe  lea     rdx, [rsp+28h+arg_8]
0x180005cc3  lea     rcx, ?ProcessesInSession@CounterHelper@@0V?$map@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@@std@@A; std::map<ulong,CounterHelper *> CounterHelper::ProcessesInSession
0x180005cca  mov     [rsp+28h+arg_8], eax
0x180005cce  call    ?erase@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::erase(ulong const &)
0x180005cd3  add     rsp, 20h
0x180005cd7  pop     rbx
0x180005cd8  retn
```
