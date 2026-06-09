# ResetToBeginning

- ea: `0x1800044f0`
- end: `0x180004581`
- name: `ResetToBeginning`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000484c`
- `0x180004ef0`
- `0x180005a1c`

## callees

- `0x1800044f0`
- `0x180007010`

## import_xrefs

- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180004500`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180004500`

## pseudocode

```c
__int64 __fastcall ResetToBeginning(_DWORD *a1)
{
  __int64 result; // rax
  __int64 i; // rbx
  __int64 v4; // rbx

  a1[6] = 0;
  a1[7] = timeGetTime();
  result = qword_18000A628[2 * (unsigned int)a1[18]] + 16LL;
  for ( i = result & ((unsigned __int128)-(__int128)(unsigned __int64)qword_18000A628[2 * (unsigned int)a1[18]] >> 64);
        i;
        i = v4 + 16 )
  {
    result = *(_QWORD *)(i + 64);
    *(_QWORD *)i = 350;
    *(_DWORD *)(i + 16) = 0;
    *(_DWORD *)(i + 56) = 0;
    *(_QWORD *)(i + 48) = 0;
    if ( result )
      result = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))result)(
                 0,
                 1,
                 *(_QWORD *)(i + 72),
                 *(int *)(i + 60),
                 0);
    v4 = *(_QWORD *)(i - 16);
    if ( !v4 )
      break;
  }
  return result;
}

```

## disassembly

```asm
0x1800044f0  push    rbx
0x1800044f2  sub     rsp, 30h
0x1800044f6  mov     rbx, rcx
0x1800044f9  mov     dword ptr [rcx+18h], 0
0x180004500  call    cs:__imp_timeGetTime
0x180004506  mov     [rbx+1Ch], eax
0x180004509  lea     rcx, qword_18000A628
0x180004510  mov     eax, [rbx+48h]
0x180004513  add     rax, rax
0x180004516  mov     rcx, [rcx+rax*8]
0x18000451a  lea     rax, [rcx+10h]
0x18000451e  neg     rcx
0x180004521  sbb     rbx, rbx
0x180004524  and     rbx, rax
0x180004527  jz      short loc_18000457B
0x180004529  mov     rax, [rbx+40h]
0x18000452d  mov     qword ptr [rbx], 15Eh
0x180004534  mov     dword ptr [rbx+10h], 0
0x18000453b  mov     dword ptr [rbx+38h], 0
0x180004542  mov     qword ptr [rbx+30h], 0
0x18000454a  test    rax, rax
0x18000454d  jz      short loc_18000456C
0x18000454f  movsxd  r9, dword ptr [rbx+3Ch]
0x180004553  mov     edx, 1
0x180004558  mov     r8, [rbx+48h]
0x18000455c  xor     ecx, ecx
0x18000455e  mov     [rsp+38h+var_18], 0
0x180004567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000456c  mov     rbx, [rbx-10h]
0x180004570  test    rbx, rbx
0x180004573  jz      short loc_18000457B
0x180004575  add     rbx, 10h
0x180004579  jnz     short loc_180004529
0x18000457b  add     rsp, 30h
0x18000457f  pop     rbx
0x180004580  retn
```
