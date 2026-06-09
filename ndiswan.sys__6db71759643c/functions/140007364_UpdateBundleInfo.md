# UpdateBundleInfo

- ea: `0x140007364`
- end: `0x14000754d`
- name: `UpdateBundleInfo`
- size: `489`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140005930`
- `0x140007bf0`
- `0x140007fb0`
- `0x14000b13c`
- `0x140024008`
- `0x140025070`
- `0x1400265dc`
- `0x140026970`
- `0x14002b270`

## callees

- `0x1400035f0`
- `0x140007364`
- `0x14000b818`
- `0x14000e400`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400074f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400074f8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007511`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007511`

## pseudocode

```c
__int64 __fastcall UpdateBundleInfo(__int64 a1)
{
  __int64 *v2; // r9
  __int64 *v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // r8d
  unsigned __int64 v6; // r10
  bool v7; // al
  unsigned int v8; // eax
  __int64 *i; // r8
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rax
  __int64 v14; // r14
  __int64 result; // rax
  __int64 v16; // rsi
  __int64 v17; // rcx

  *(_DWORD *)(a1 + 336) = 0;
  *(_DWORD *)(a1 + 328) = 0;
  *(_DWORD *)(a1 + 368) = 0;
  *(_DWORD *)(a1 + 360) = 0;
  *(_DWORD *)(a1 + 20) = 1;
  *(_DWORD *)(a1 + 164) = 0;
  if ( *(_DWORD *)(a1 + 64) )
  {
    v2 = (__int64 *)(a1 + 48);
    v3 = *(__int64 **)(a1 + 48);
    v4 = *((_DWORD *)v3 + 34);
    v5 = *((_DWORD *)v3 + 38);
    *(_QWORD *)(a1 + 156) = 0;
    if ( v3 != v2 )
    {
      v6 = v4;
      do
      {
        if ( *((_DWORD *)v3 + 5) == 2 )
          *(_DWORD *)(a1 + 20) = 2;
        v7 = (unsigned int)(100 * (unsigned __int64)*((unsigned int *)v3 + 34) / v6) > glMinLinkBandwidth;
        *((_BYTE *)v3 + 200) = v7;
        if ( v7 )
        {
          *(_DWORD *)(a1 + 160) += *((_DWORD *)v3 + 51);
          *(_DWORD *)(a1 + 164) += *((_DWORD *)v3 + 52);
          if ( *((_BYTE *)v3 + 201) )
            ++*(_DWORD *)(a1 + 156);
          *(_DWORD *)(a1 + 336) += *((_DWORD *)v3 + 34);
          *(_DWORD *)(a1 + 368) += *((_DWORD *)v3 + 42);
        }
        v8 = *((_DWORD *)v3 + 38);
        v3 = (__int64 *)*v3;
        if ( v8 < v5 )
          v5 = v8;
      }
      while ( v3 != v2 );
    }
    *(_DWORD *)(a1 + 352) = v5;
    for ( i = (__int64 *)*v2; i != v2; i = (__int64 *)*i )
    {
      v10 = *(unsigned int *)(a1 + 336);
      if ( !(_DWORD)v10 || (v11 = 100 * (unsigned __int64)*((unsigned int *)i + 34) / v10) == 0 )
        LODWORD(v11) = 1;
      *((_DWORD *)i + 48) = v11;
      v12 = *(unsigned int *)(a1 + 368);
      if ( !(_DWORD)v12 || (v13 = 100 * (unsigned __int64)*((unsigned int *)i + 42) / v12) == 0 )
        LODWORD(v13) = 1;
      *((_DWORD *)i + 49) = v13;
    }
    *(_QWORD *)(a1 + 88) = *v2;
  }
  v14 = a1 + 280;
  for ( result = *(_QWORD *)(a1 + 280); result != v14; result = *(_QWORD *)result )
    _InterlockedIncrement((volatile signed __int32 *)(result + 24));
  v16 = *(_QWORD *)(a1 + 288);
  while ( v16 != v14 )
  {
    if ( *(_DWORD *)(a1 + 20) == 2 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 1768), *(_BYTE *)(a1 + 1776));
      DoLineUpToProtocol(v16, 0);
      *(_BYTE *)(a1 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1768));
    }
    else
    {
      FlushProtocolPacketQueue(v16);
    }
    v17 = v16;
    v16 = *(_QWORD *)(v16 + 8);
    result = DereferenceRefCount(v17 + 24);
  }
  return result;
}

```

## disassembly

```asm
0x140007364  push    rbx
0x140007366  push    rsi
0x140007367  push    rdi
0x140007368  push    r14
0x14000736a  sub     rsp, 28h
0x14000736e  xor     r11d, r11d
0x140007371  mov     rdi, rcx
0x140007374  mov     [rcx+150h], r11d
0x14000737b  mov     [rcx+148h], r11d
0x140007382  mov     [rcx+170h], r11d
0x140007389  lea     ebx, [r11+1]
0x14000738d  mov     [rcx+168h], r11d
0x140007394  mov     [rcx+14h], ebx
0x140007397  mov     [rcx+0A4h], r11d
0x14000739e  cmp     [rcx+40h], r11d
0x1400073a2  jz      loc_1400074C1
0x1400073a8  lea     r9, [rcx+30h]
0x1400073ac  mov     rcx, [r9]
0x1400073af  mov     eax, [rcx+88h]
0x1400073b5  mov     r8d, [rcx+98h]
0x1400073bc  mov     [rdi+9Ch], r11
0x1400073c3  cmp     rcx, r9
0x1400073c6  jz      loc_140007456
0x1400073cc  mov     r10d, eax
0x1400073cf  cmp     dword ptr [rcx+14h], 2
0x1400073d3  jnz     short loc_1400073DC
0x1400073d5  mov     dword ptr [rdi+14h], 2
0x1400073dc  mov     eax, [rcx+88h]
0x1400073e2  xor     edx, edx
0x1400073e4  imul    rax, 64h ; 'd'
0x1400073e8  div     r10
0x1400073eb  cmp     eax, cs:glMinLinkBandwidth
0x1400073f1  setnbe  al
0x1400073f4  mov     [rcx+0C8h], al
0x1400073fa  test    al, al
0x1400073fc  jz      short loc_14000743D
0x1400073fe  mov     eax, [rcx+0CCh]
0x140007404  add     [rdi+0A0h], eax
0x14000740a  mov     eax, [rcx+0D0h]
0x140007410  add     [rdi+0A4h], eax
0x140007416  cmp     [rcx+0C9h], r11b
0x14000741d  jz      short loc_140007425
0x14000741f  add     [rdi+9Ch], ebx
0x140007425  mov     eax, [rcx+88h]
0x14000742b  add     [rdi+150h], eax
0x140007431  mov     eax, [rcx+0A8h]
0x140007437  add     [rdi+170h], eax
0x14000743d  mov     eax, [rcx+98h]
0x140007443  cmp     eax, r8d
0x140007446  mov     rcx, [rcx]
0x140007449  cmovb   r8d, eax
0x14000744d  cmp     rcx, r9
0x140007450  jnz     loc_1400073CF
0x140007456  mov     [rdi+160h], r8d
0x14000745d  mov     r8, [r9]
0x140007460  jmp     short loc_1400074B5
0x140007462  mov     ecx, [rdi+150h]
0x140007468  test    ecx, ecx
0x14000746a  jz      short loc_140007481
0x14000746c  mov     eax, [r8+88h]
0x140007473  xor     edx, edx
0x140007475  imul    rax, 64h ; 'd'
0x140007479  div     rcx
0x14000747c  test    rax, rax
0x14000747f  jnz     short loc_140007483
0x140007481  mov     eax, ebx
0x140007483  mov     [r8+0C0h], eax
0x14000748a  mov     ecx, [rdi+170h]
0x140007490  test    ecx, ecx
0x140007492  jz      short loc_1400074A9
0x140007494  mov     eax, [r8+0A8h]
0x14000749b  xor     edx, edx
0x14000749d  imul    rax, 64h ; 'd'
0x1400074a1  div     rcx
0x1400074a4  test    rax, rax
0x1400074a7  jnz     short loc_1400074AB
0x1400074a9  mov     eax, ebx
0x1400074ab  mov     [r8+0C4h], eax
0x1400074b2  mov     r8, [r8]
0x1400074b5  cmp     r8, r9
0x1400074b8  jnz     short loc_140007462
0x1400074ba  mov     rax, [r9]
0x1400074bd  mov     [rdi+58h], rax
0x1400074c1  lea     r14, [rdi+118h]
0x1400074c8  mov     rax, [r14]
0x1400074cb  jmp     short loc_1400074D4
0x1400074cd  lock inc dword ptr [rax+18h]
0x1400074d1  mov     rax, [rax]
0x1400074d4  cmp     rax, r14
0x1400074d7  jnz     short loc_1400074CD
0x1400074d9  mov     rsi, [rdi+120h]
0x1400074e0  jmp     short loc_14000753D
0x1400074e2  cmp     dword ptr [rdi+14h], 2
0x1400074e6  jnz     short loc_140007525
0x1400074e8  mov     dl, [rdi+6F0h]; NewIrql
0x1400074ee  lea     rbx, [rdi+6E8h]
0x1400074f5  mov     rcx, rbx; SpinLock
0x1400074f8  call    cs:__imp_KeReleaseSpinLock
0x1400074ff  nop     dword ptr [rax+rax+00h]
0x140007504  xor     edx, edx
0x140007506  mov     rcx, rsi
0x140007509  call    DoLineUpToProtocol
0x14000750e  mov     rcx, rbx; SpinLock
0x140007511  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007518  nop     dword ptr [rax+rax+00h]
0x14000751d  mov     [rdi+6F0h], al
0x140007523  jmp     short loc_14000752D
0x140007525  mov     rcx, rsi
0x140007528  call    FlushProtocolPacketQueue
0x14000752d  mov     rcx, rsi
0x140007530  mov     rsi, [rsi+8]
0x140007534  add     rcx, 18h
0x140007538  call    DereferenceRefCount
0x14000753d  cmp     rsi, r14
0x140007540  jnz     short loc_1400074E2
0x140007542  add     rsp, 28h
0x140007546  pop     r14
0x140007548  pop     rdi
0x140007549  pop     rsi
0x14000754a  pop     rbx
0x14000754b  retn
```
