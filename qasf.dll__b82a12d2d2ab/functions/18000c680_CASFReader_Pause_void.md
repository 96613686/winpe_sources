# CASFReader::Pause(void)

- ea: `0x18000c680`
- end: `0x18000c73f`
- name: `?Pause@CASFReader@@UEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(CASFReader *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000c680`
- `0x18000d3ec`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::Pause(CASFReader *this)
{
  __int64 v2; // rcx
  int started; // edi
  __int64 v5; // rsi
  _QWORD *v6; // rcx

  v2 = *((_QWORD *)this + 55);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 40LL))(v2);
  if ( !*((_QWORD *)this + 40) )
    return 2147500037LL;
  started = 0;
  if ( *((_DWORD *)this + 4) )
  {
    if ( *((_DWORD *)this + 4) == 2 )
      *((_DWORD *)this + 4) = 1;
  }
  else
  {
    v5 = *((_QWORD *)this + 32);
    if ( v5 )
    {
      while ( started >= 0 )
      {
        v6 = *(_QWORD **)(v5 + 16);
        v5 = *(_QWORD *)(v5 + 8);
        if ( v6[6] )
          started = (*(__int64 (__fastcall **)(_QWORD *))(*v6 + 40LL))(v6);
        if ( !v5 )
        {
          if ( started < 0 )
            break;
          goto LABEL_12;
        }
      }
    }
    else
    {
LABEL_12:
      started = CASFReader::StartPushing((CASFReader *)((char *)this - 24));
    }
    *((_DWORD *)this + 4) = 1;
    if ( started < 0 )
      (*(void (__fastcall **)(CASFReader *))(*(_QWORD *)this + 32LL))(this);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000c680  push    rbx
0x18000c682  push    rbp
0x18000c683  push    rsi
0x18000c684  push    rdi
0x18000c685  sub     rsp, 28h
0x18000c689  mov     rbx, rcx
0x18000c68c  mov     rcx, [rcx+1B8h]
0x18000c693  test    rcx, rcx
0x18000c696  jz      short loc_18000C6A9
0x18000c698  mov     rax, [rcx]
0x18000c69b  mov     rax, [rax+28h]
0x18000c69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6a4  jmp     loc_18000C736
0x18000c6a9  cmp     qword ptr [rbx+140h], 0
0x18000c6b1  jnz     short loc_18000C6BA
0x18000c6b3  mov     eax, 80004005h
0x18000c6b8  jmp     short loc_18000C736
0x18000c6ba  xor     edi, edi
0x18000c6bc  cmp     [rbx+10h], edi
0x18000c6bf  jnz     short loc_18000C727
0x18000c6c1  mov     rsi, [rbx+100h]
0x18000c6c8  test    rsi, rsi
0x18000c6cb  jz      short loc_18000C700
0x18000c6cd  test    edi, edi
0x18000c6cf  js      short loc_18000C70B
0x18000c6d1  test    rsi, rsi
0x18000c6d4  jnz     short loc_18000C6DA
0x18000c6d6  xor     ecx, ecx
0x18000c6d8  jmp     short loc_18000C6E2
0x18000c6da  mov     rcx, [rsi+10h]
0x18000c6de  mov     rsi, [rsi+8]
0x18000c6e2  cmp     qword ptr [rcx+30h], 0
0x18000c6e7  jz      short loc_18000C6F7
0x18000c6e9  mov     rax, [rcx]
0x18000c6ec  mov     rax, [rax+28h]
0x18000c6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6f5  mov     edi, eax
0x18000c6f7  test    rsi, rsi
0x18000c6fa  jnz     short loc_18000C6CD
0x18000c6fc  test    edi, edi
0x18000c6fe  js      short loc_18000C70B
0x18000c700  lea     rcx, [rbx-18h]; this
0x18000c704  call    ?StartPushing@CASFReader@@AEAAJXZ; CASFReader::StartPushing(void)
0x18000c709  mov     edi, eax
0x18000c70b  mov     dword ptr [rbx+10h], 1
0x18000c712  test    edi, edi
0x18000c714  jns     short loc_18000C734
0x18000c716  mov     rax, [rbx]
0x18000c719  mov     rcx, rbx
0x18000c71c  mov     rax, [rax+20h]
0x18000c720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c725  jmp     short loc_18000C734
0x18000c727  cmp     dword ptr [rbx+10h], 2
0x18000c72b  jnz     short loc_18000C734
0x18000c72d  mov     dword ptr [rbx+10h], 1
0x18000c734  mov     eax, edi
0x18000c736  add     rsp, 28h
0x18000c73a  pop     rdi
0x18000c73b  pop     rsi
0x18000c73c  pop     rbp
0x18000c73d  pop     rbx
0x18000c73e  retn
```
