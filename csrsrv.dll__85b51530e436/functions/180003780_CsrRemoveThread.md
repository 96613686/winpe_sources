# CsrRemoveThread

- ea: `0x180003780`
- end: `0x180003828`
- name: `CsrRemoveThread`
- size: `168`
- prototype: `int __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002a00`
- `0x180002c90`
- `0x1800036c0`

## callees

- `0x180003780`
- `0x180003c20`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180003813`
- `ntdll!RtlEnterCriticalSection` at `0x180003813`

## pseudocode

```c
int __fastcall CsrRemoveThread(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rax
  _QWORD *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  _QWORD *v7; // rdx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  v2 = a1 + 8;
  if ( *(_QWORD *)(v1 + 8) != a1 + 8 )
    goto LABEL_12;
  v4 = *(_QWORD **)(a1 + 16);
  if ( *v4 != v2 )
    goto LABEL_12;
  *v4 = v1;
  *(_QWORD *)(v1 + 8) = v4;
  v5 = a1 + 24;
  v6 = *(_QWORD *)(a1 + 24);
  if ( v6 )
  {
    if ( *(_QWORD *)(v6 + 8) == v5 )
    {
      v7 = *(_QWORD **)(a1 + 32);
      if ( *v7 == v5 )
      {
        *v7 = v6;
        *(_QWORD *)(v6 + 8) = v7;
        goto LABEL_7;
      }
    }
LABEL_12:
    __fastfail(3u);
  }
LABEL_7:
  v8 = *(_QWORD *)(a1 + 56);
  v9 = (_QWORD *)(v8 + 32);
  if ( (_QWORD *)*v9 == v9 )
  {
    LODWORD(v9) = *(_DWORD *)(v8 + 92);
    if ( ((unsigned __int16)v9 & 0x8000) == 0 )
    {
      *(_DWORD *)(v8 + 92) = (unsigned int)v9 | 8;
      v10 = *(_QWORD *)(a1 + 56);
      LODWORD(v9) = _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 100), 0xFFFFFFFF);
      if ( (_DWORD)v9 == 1 )
      {
        CsrProcessRefcountZero(v10);
        LODWORD(v9) = RtlEnterCriticalSection(&CsrProcessStructureLock);
      }
    }
  }
  *(_DWORD *)(a1 + 72) |= 2u;
  return (int)v9;
}

```

## disassembly

```asm
0x180003780  push    rbx
0x180003782  sub     rsp, 20h
0x180003786  mov     rdx, [rcx+8]
0x18000378a  lea     rax, [rcx+8]
0x18000378e  mov     rbx, rcx
0x180003791  cmp     [rdx+8], rax
0x180003795  jnz     loc_180003821
0x18000379b  mov     rcx, [rax+8]
0x18000379f  cmp     [rcx], rax
0x1800037a2  jnz     short loc_180003821
0x1800037a4  mov     [rcx], rdx
0x1800037a7  mov     [rdx+8], rcx
0x1800037ab  lea     rcx, [rbx+18h]
0x1800037af  mov     rax, [rcx]
0x1800037b2  test    rax, rax
0x1800037b5  jz      short loc_1800037CD
0x1800037b7  cmp     [rax+8], rcx
0x1800037bb  jnz     short loc_180003821
0x1800037bd  mov     rdx, [rcx+8]
0x1800037c1  cmp     [rdx], rcx
0x1800037c4  jnz     short loc_180003821
0x1800037c6  mov     [rdx], rax
0x1800037c9  mov     [rax+8], rdx
0x1800037cd  mov     rcx, [rbx+38h]
0x1800037d1  lea     rax, [rcx+20h]
0x1800037d5  cmp     [rax], rax
0x1800037d8  jz      short loc_1800037E5
0x1800037da  or      dword ptr [rbx+48h], 2
0x1800037de  add     rsp, 20h
0x1800037e2  pop     rbx
0x1800037e3  retn
0x1800037e5  mov     eax, [rcx+5Ch]
0x1800037e8  bt      eax, 0Fh
0x1800037ec  jb      short loc_1800037DA
0x1800037ee  or      eax, 8
0x1800037f1  mov     [rcx+5Ch], eax
0x1800037f4  mov     eax, 0FFFFFFFFh
0x1800037f9  mov     rcx, [rbx+38h]
0x1800037fd  lock xadd [rcx+64h], eax
0x180003802  cmp     eax, 1
0x180003805  jnz     short loc_1800037DA
0x180003807  call    CsrProcessRefcountZero
0x18000380c  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003813  call    cs:__imp_RtlEnterCriticalSection
0x18000381a  nop     dword ptr [rax+rax+00h]
0x18000381f  jmp     short loc_1800037DA
0x180003821  mov     ecx, 3
0x180003826  int     29h; Win8: RtlFailFast(ecx)
```
