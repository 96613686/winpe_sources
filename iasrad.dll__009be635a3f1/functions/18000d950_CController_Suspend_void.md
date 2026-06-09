# CController::Suspend(void)

- ea: `0x18000d950`
- end: `0x18000dbe5`
- name: `?Suspend@CController@@UEAAJXZ`
- size: `661`
- prototype: `__int64 __fastcall(CController *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800094e4`
- `0x18000d950`
- `0x18000dc54`
- `0x18001a27c`
- `0x18001d31c`
- `0x180030010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18000dad9`
- `KERNEL32!Sleep` at `0x18000db66`
- `KERNEL32!Sleep` at `0x18000dad9`
- `KERNEL32!Sleep` at `0x18000db66`

## string_xrefs

- `0x18000d991`: `Suspending Radius component...`
- `0x18000d9e6`: `Radius component can not be suspended in current state`
- `0x18000db30`: `Worker thread active:%d`
- `0x18000dbaf`: `Radius component suspended.`

## pseudocode

```c
__int64 __fastcall CController::Suspend(CController *this)
{
  PVOID *v2; // rax
  int v3; // ecx
  int v5; // edi

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Suspending Radius component...");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = *((_DWORD *)this + 322);
  if ( v3 == 3 )
    return 0;
  if ( v3 == 2 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 96LL))(*((_QWORD *)this + 23));
    if ( v5 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Infobase suspend failed");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9)) )
      v5 = -2147467259;
    while ( g_lPacketCount )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Packet Left to process:%d");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          (unsigned int)WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids,
          (unsigned int)"NPSRAD",
          g_lPacketCount);
      }
      Sleep(0x32u);
    }
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 16LL))(*((_QWORD *)this + 18)) )
      v5 = -2147467259;
    *(_QWORD *)(*((_QWORD *)this + 17) + 16LL) = 0;
    while ( g_lThreadCount )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Worker thread active:%d");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          (unsigned int)WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids,
          (unsigned int)"NPSRAD",
          g_lThreadCount);
      }
      Sleep(0x32u);
    }
    CPorts::CloseSockets((CController *)((char *)this + 192));
    CPorts::CloseSockets((CController *)((char *)this + 728));
    *((_DWORD *)this + 322) = 3;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Radius component suspended.");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    return (unsigned int)v5;
  }
  else
  {
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 2u && (*((_DWORD *)v2 + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Radius component can not be suspended in current state");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    }
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18000d950  push    rbx
0x18000d952  push    rbp
0x18000d953  push    rsi
0x18000d954  push    rdi
0x18000d955  push    r14
0x18000d957  push    r15
0x18000d959  sub     rsp, 38h
0x18000d95d  mov     rbx, rcx
0x18000d960  mov     rax, cs:WPP_GLOBAL_Control
0x18000d967  lea     rbp, WPP_GLOBAL_Control
0x18000d96e  lea     r14, aNpsrad; "NPSRAD"
0x18000d975  mov     esi, 100h
0x18000d97a  lea     r15, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000d981  cmp     rax, rbp
0x18000d984  jz      short loc_18000D9BF
0x18000d986  cmp     byte ptr [rax+19h], 4
0x18000d98a  jb      short loc_18000D9BF
0x18000d98c  test    [rax+1Ch], esi
0x18000d98f  jz      short loc_18000D9BF
0x18000d991  lea     rcx, aSuspendingRadi; "Suspending Radius component..."
0x18000d998  call    WppDbgPrint
0x18000d99d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9a4  mov     edx, 39h ; '9'
0x18000d9a9  mov     r9, r14
0x18000d9ac  mov     r8, r15
0x18000d9af  mov     rcx, [rcx+10h]
0x18000d9b3  call    WPP_SF_s
0x18000d9b8  mov     rax, cs:WPP_GLOBAL_Control
0x18000d9bf  mov     ecx, [rbx+508h]
0x18000d9c5  cmp     ecx, 3
0x18000d9c8  jnz     short loc_18000D9D1
0x18000d9ca  xor     eax, eax
0x18000d9cc  jmp     loc_18000DBD8
0x18000d9d1  cmp     ecx, 2
0x18000d9d4  jz      short loc_18000DA17
0x18000d9d6  cmp     rax, rbp
0x18000d9d9  jz      short loc_18000DA0D
0x18000d9db  cmp     byte ptr [rax+19h], 2
0x18000d9df  jb      short loc_18000DA0D
0x18000d9e1  test    [rax+1Ch], esi
0x18000d9e4  jz      short loc_18000DA0D
0x18000d9e6  lea     rcx, aRadiusComponen_1; "Radius component can not be suspended i"...
0x18000d9ed  call    WppDbgPrint
0x18000d9f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9f9  mov     edx, 3Ah ; ':'
0x18000d9fe  mov     r9, r14
0x18000da01  mov     r8, r15
0x18000da04  mov     rcx, [rcx+10h]
0x18000da08  call    WPP_SF_s
0x18000da0d  mov     eax, 8000FFFFh
0x18000da12  jmp     loc_18000DBD8
0x18000da17  mov     rcx, [rbx+0B8h]
0x18000da1e  mov     rax, [rcx]
0x18000da21  mov     rax, [rax+60h]
0x18000da25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da2a  mov     edi, eax
0x18000da2c  test    eax, eax
0x18000da2e  jns     short loc_18000DA6E
0x18000da30  mov     rax, cs:WPP_GLOBAL_Control
0x18000da37  cmp     rax, rbp
0x18000da3a  jz      short loc_18000DA6E
0x18000da3c  cmp     byte ptr [rax+19h], 2
0x18000da40  jb      short loc_18000DA6E
0x18000da42  test    [rax+1Ch], esi
0x18000da45  jz      short loc_18000DA6E
0x18000da47  lea     rcx, aInfobaseSuspen; "Infobase suspend failed"
0x18000da4e  call    WppDbgPrint
0x18000da53  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da5a  mov     edx, 3Bh ; ';'
0x18000da5f  mov     r9, r14
0x18000da62  mov     r8, r15
0x18000da65  mov     rcx, [rcx+10h]
0x18000da69  call    WPP_SF_s
0x18000da6e  mov     rcx, [rbx+48h]
0x18000da72  mov     rax, [rcx]
0x18000da75  mov     rax, [rax+10h]
0x18000da79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da7e  test    eax, eax
0x18000da80  mov     ecx, 80004005h
0x18000da85  cmovz   edi, ecx
0x18000da88  jmp     short loc_18000DADF
0x18000da8a  mov     rax, cs:WPP_GLOBAL_Control
0x18000da91  cmp     rax, rbp
0x18000da94  jz      short loc_18000DAD4
0x18000da96  cmp     byte ptr [rax+19h], 4
0x18000da9a  jb      short loc_18000DAD4
0x18000da9c  test    [rax+1Ch], esi
0x18000da9f  jz      short loc_18000DAD4
0x18000daa1  mov     edx, ecx
0x18000daa3  lea     rcx, aPacketLeftToPr; "Packet Left to process:%d"
0x18000daaa  call    WppDbgPrint
0x18000daaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dab6  mov     edx, 3Ch ; '<'
0x18000dabb  mov     eax, cs:?g_lPacketCount@@3JA; long g_lPacketCount
0x18000dac1  mov     r9, r14
0x18000dac4  mov     r8, r15
0x18000dac7  mov     [rsp+68h+var_48], eax
0x18000dacb  mov     rcx, [rcx+10h]
0x18000dacf  call    WPP_SF_sd
0x18000dad4  mov     ecx, 32h ; '2'; dwMilliseconds
0x18000dad9  call    cs:__imp_Sleep
0x18000dadf  mov     ecx, cs:?g_lPacketCount@@3JA; long g_lPacketCount
0x18000dae5  test    ecx, ecx
0x18000dae7  jnz     short loc_18000DA8A
0x18000dae9  mov     rcx, [rbx+90h]
0x18000daf0  mov     rax, [rcx]
0x18000daf3  mov     rax, [rax+10h]
0x18000daf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dafc  test    eax, eax
0x18000dafe  mov     eax, 80004005h
0x18000db03  cmovz   edi, eax
0x18000db06  mov     rax, [rbx+88h]
0x18000db0d  mov     qword ptr [rax+10h], 0
0x18000db15  jmp     short loc_18000DB6C
0x18000db17  mov     rax, cs:WPP_GLOBAL_Control
0x18000db1e  cmp     rax, rbp
0x18000db21  jz      short loc_18000DB61
0x18000db23  cmp     byte ptr [rax+19h], 4
0x18000db27  jb      short loc_18000DB61
0x18000db29  test    [rax+1Ch], esi
0x18000db2c  jz      short loc_18000DB61
0x18000db2e  mov     edx, ecx
0x18000db30  lea     rcx, aWorkerThreadAc; "Worker thread active:%d"
0x18000db37  call    WppDbgPrint
0x18000db3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db43  mov     edx, 3Dh ; '='
0x18000db48  mov     eax, cs:?g_lThreadCount@@3JA; long g_lThreadCount
0x18000db4e  mov     r9, r14
0x18000db51  mov     r8, r15
0x18000db54  mov     [rsp+68h+var_48], eax
0x18000db58  mov     rcx, [rcx+10h]
0x18000db5c  call    WPP_SF_sd
0x18000db61  mov     ecx, 32h ; '2'; dwMilliseconds
0x18000db66  call    cs:__imp_Sleep
0x18000db6c  mov     ecx, cs:?g_lThreadCount@@3JA; long g_lThreadCount
0x18000db72  test    ecx, ecx
0x18000db74  jnz     short loc_18000DB17
0x18000db76  lea     rcx, [rbx+0C0h]; this
0x18000db7d  call    ?CloseSockets@CPorts@@QEAAXXZ; CPorts::CloseSockets(void)
0x18000db82  lea     rcx, [rbx+2D8h]; this
0x18000db89  call    ?CloseSockets@CPorts@@QEAAXXZ; CPorts::CloseSockets(void)
0x18000db8e  mov     dword ptr [rbx+508h], 3
0x18000db98  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db9f  cmp     rcx, rbp
0x18000dba2  jz      short loc_18000DBD6
0x18000dba4  cmp     byte ptr [rcx+19h], 4
0x18000dba8  jb      short loc_18000DBD6
0x18000dbaa  test    [rcx+1Ch], esi
0x18000dbad  jz      short loc_18000DBD6
0x18000dbaf  lea     rcx, aRadiusComponen_4; "Radius component suspended."
0x18000dbb6  call    WppDbgPrint
0x18000dbbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbc2  mov     edx, 3Eh ; '>'
0x18000dbc7  mov     r9, r14
0x18000dbca  mov     r8, r15
0x18000dbcd  mov     rcx, [rcx+10h]
0x18000dbd1  call    WPP_SF_s
0x18000dbd6  mov     eax, edi
0x18000dbd8  add     rsp, 38h
0x18000dbdc  pop     r15
0x18000dbde  pop     r14
0x18000dbe0  pop     rdi
0x18000dbe1  pop     rsi
0x18000dbe2  pop     rbp
0x18000dbe3  pop     rbx
0x18000dbe4  retn
```
