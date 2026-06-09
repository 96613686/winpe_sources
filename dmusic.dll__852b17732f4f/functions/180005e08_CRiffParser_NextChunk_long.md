# CRiffParser::NextChunk(long *)

- ea: `0x180005e08`
- end: `0x180005f16`
- name: `?NextChunk@CRiffParser@@QEAAHPEAJ@Z`
- size: `270`
- prototype: `__int64 __fastcall(CRiffParser *__hidden this, int *)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x180009b30`
- `0x18000b730`
- `0x18000baf0`
- `0x18000bd1c`
- `0x18000bf60`
- `0x18000c4f0`
- `0x18000c5f8`
- `0x18000c8b0`
- `0x18000cd90`
- `0x18000dda4`
- `0x18000e178`
- `0x180010938`
- `0x180014834`

## callees

- `0x180005838`
- `0x180005e08`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CRiffParser::NextChunk(CRiffParser *this, int *a2)
{
  __int64 v4; // r10
  __int64 v5; // rdx
  int v6; // ecx
  int v7; // edx
  _DWORD *v8; // r8

  if ( *a2 < 0 )
  {
    if ( *((_DWORD *)this + 10) )
    {
      *((_DWORD *)this + 9) = 1;
      *a2 = CRiffParser::LeaveChunk(this);
    }
    else
    {
      CRiffParser::LeaveChunk(this);
    }
  }
  else
  {
    if ( *((_DWORD *)this + 1) )
      *((_DWORD *)this + 1) = 0;
    else
      *a2 = CRiffParser::LeaveChunk(this);
    v4 = *((_QWORD *)this + 2);
    if ( v4 )
    {
      v5 = *((_QWORD *)this + 3);
      v6 = 0;
      LOBYTE(v6) = v5 ? *(_DWORD *)(v5 + 12) < (unsigned int)(*(_DWORD *)(v5 + 4) - 8) : *(_DWORD *)(v4 + 12) == 0;
      if ( v6 && *a2 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 1) + 24LL))(
               *((_QWORD *)this + 1),
               *((_QWORD *)this + 2),
               8,
               0);
        if ( v7 >= 0 )
        {
          *(_DWORD *)(*((_QWORD *)this + 2) + 12LL) = 0;
          v8 = (_DWORD *)*((_QWORD *)this + 2);
          if ( *v8 == 1179011410 || *v8 == 1414744396 )
          {
            v7 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, __int64))(**((_QWORD **)this + 1) + 24LL))(
                   *((_QWORD *)this + 1),
                   v8 + 2,
                   4);
            if ( v7 >= 0 )
              *(_DWORD *)(*((_QWORD *)this + 2) + 12LL) += 4;
          }
        }
        *a2 = v7;
        if ( v7 >= 0 )
          return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180005e08  mov     [rsp+arg_0], rbx
0x180005e0d  push    rdi
0x180005e0e  sub     rsp, 30h
0x180005e12  cmp     dword ptr [rdx], 0
0x180005e15  mov     rdi, rdx
0x180005e18  mov     rbx, rcx
0x180005e1b  jl      loc_180005EEE
0x180005e21  cmp     dword ptr [rcx+4], 0
0x180005e25  jz      short loc_180005E30
0x180005e27  mov     dword ptr [rcx+4], 0
0x180005e2e  jmp     short loc_180005E37
0x180005e30  call    ?LeaveChunk@CRiffParser@@QEAAJXZ; CRiffParser::LeaveChunk(void)
0x180005e35  mov     [rdi], eax
0x180005e37  mov     r10, [rbx+10h]
0x180005e3b  test    r10, r10
0x180005e3e  jz      loc_180005F09
0x180005e44  mov     rdx, [rbx+18h]
0x180005e48  xor     ecx, ecx
0x180005e4a  mov     r8d, 8
0x180005e50  test    rdx, rdx
0x180005e53  jz      short loc_180005E63
0x180005e55  mov     eax, [rdx+4]
0x180005e58  sub     eax, r8d
0x180005e5b  cmp     [rdx+0Ch], eax
0x180005e5e  setb    cl
0x180005e61  jmp     short loc_180005E6A
0x180005e63  cmp     [r10+0Ch], ecx
0x180005e67  setz    cl
0x180005e6a  test    ecx, ecx
0x180005e6c  jz      loc_180005F09
0x180005e72  cmp     dword ptr [rdi], 0
0x180005e75  jl      loc_180005F09
0x180005e7b  mov     rcx, [rbx+8]
0x180005e7f  xor     r9d, r9d
0x180005e82  mov     rdx, r10
0x180005e85  mov     rax, [rcx]
0x180005e88  mov     rax, [rax+18h]
0x180005e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e91  mov     edx, eax
0x180005e93  test    eax, eax
0x180005e95  js      short loc_180005EE1
0x180005e97  mov     rcx, [rbx+10h]
0x180005e9b  mov     dword ptr [rcx+0Ch], 0
0x180005ea2  mov     r8, [rbx+10h]
0x180005ea6  cmp     dword ptr [r8], 46464952h
0x180005ead  jz      short loc_180005EB8
0x180005eaf  cmp     dword ptr [r8], 5453494Ch
0x180005eb6  jnz     short loc_180005EE1
0x180005eb8  mov     rcx, [rbx+8]
0x180005ebc  lea     rdx, [r8+8]
0x180005ec0  xor     r9d, r9d
0x180005ec3  mov     rax, [rcx]
0x180005ec6  lea     r8d, [r9+4]
0x180005eca  mov     rax, [rax+18h]
0x180005ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed3  mov     edx, eax
0x180005ed5  test    eax, eax
0x180005ed7  js      short loc_180005EE1
0x180005ed9  mov     rax, [rbx+10h]
0x180005edd  add     dword ptr [rax+0Ch], 4
0x180005ee1  mov     [rdi], edx
0x180005ee3  test    edx, edx
0x180005ee5  jl      short loc_180005F09
0x180005ee7  mov     eax, 1
0x180005eec  jmp     short loc_180005F0B
0x180005eee  cmp     dword ptr [rcx+28h], 0
0x180005ef2  jz      short loc_180005F04
0x180005ef4  mov     dword ptr [rcx+24h], 1
0x180005efb  call    ?LeaveChunk@CRiffParser@@QEAAJXZ; CRiffParser::LeaveChunk(void)
0x180005f00  mov     [rdi], eax
0x180005f02  jmp     short loc_180005F09
0x180005f04  call    ?LeaveChunk@CRiffParser@@QEAAJXZ; CRiffParser::LeaveChunk(void)
0x180005f09  xor     eax, eax
0x180005f0b  mov     rbx, [rsp+38h+arg_0]
0x180005f10  add     rsp, 30h
0x180005f14  pop     rdi
0x180005f15  retn
```
