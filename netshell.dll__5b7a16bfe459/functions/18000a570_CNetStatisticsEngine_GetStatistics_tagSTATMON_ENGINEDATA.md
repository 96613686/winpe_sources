# CNetStatisticsEngine::GetStatistics(tagSTATMON_ENGINEDATA * *)

- ea: `0x18000a570`
- end: `0x18000a64e`
- name: `?GetStatistics@CNetStatisticsEngine@@UEAAJPEAPEAUtagSTATMON_ENGINEDATA@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(CNetStatisticsEngine *__hidden this, struct tagSTATMON_ENGINEDATA **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000a570`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a62f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a62f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a596`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a596`
- `ole32!CoTaskMemAlloc` at `0x18000a5d4`
- `ole32!CoTaskMemAlloc` at `0x18000a5d4`

## pseudocode

```c
__int64 __fastcall CNetStatisticsEngine::GetStatistics(CNetStatisticsEngine *this, struct tagSTATMON_ENGINEDATA **a2)
{
  unsigned int v4; // ebx
  struct tagSTATMON_ENGINEDATA *v5; // rbp
  __int64 *v6; // rcx
  __int64 v7; // rax
  struct tagSTATMON_ENGINEDATA *v8; // rcx
  _OWORD *v9; // rax
  int v11; // [rsp+48h] [rbp+10h] BYREF
  int v12; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    v4 = 0;
    v5 = 0;
    EnterCriticalSection(&g_csStatmonData);
    v6 = (__int64 *)((char *)this - 32);
    if ( !*((_QWORD *)this + 12) )
    {
      v7 = *v6;
      v12 = 0;
      v11 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64 *, int *, int *))(v7 + 72))(v6, &v12, &v11);
    }
    if ( *((_QWORD *)this + 12) )
    {
      v8 = (struct tagSTATMON_ENGINEDATA *)CoTaskMemAlloc(0x70u);
      if ( v8 )
      {
        v9 = (_OWORD *)*((_QWORD *)this + 12);
        v4 = 0;
        v5 = v8;
        *(_OWORD *)v8 = *v9;
        *((_OWORD *)v8 + 1) = v9[1];
        *((_OWORD *)v8 + 2) = v9[2];
        *((_OWORD *)v8 + 3) = v9[3];
        *((_OWORD *)v8 + 4) = v9[4];
        *((_OWORD *)v8 + 5) = v9[5];
        *((_OWORD *)v8 + 6) = v9[6];
      }
      else
      {
        v4 = -2147024882;
      }
    }
    LeaveCriticalSection(&g_csStatmonData);
    *a2 = v5;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18000a570  mov     [rsp+arg_0], rbx
0x18000a575  push    rbp
0x18000a576  push    rsi
0x18000a577  push    rdi
0x18000a578  sub     rsp, 20h
0x18000a57c  mov     rsi, rdx
0x18000a57f  mov     rdi, rcx
0x18000a582  test    rdx, rdx
0x18000a585  jz      loc_18000A63A
0x18000a58b  lea     rcx, ?g_csStatmonData@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a592  xor     ebx, ebx
0x18000a594  xor     ebp, ebp
0x18000a596  call    cs:__imp_EnterCriticalSection
0x18000a59c  lea     rcx, [rdi-20h]
0x18000a5a0  cmp     [rcx+80h], rbx
0x18000a5a7  jnz     short loc_18000A5C9
0x18000a5a9  mov     rax, [rcx]
0x18000a5ac  lea     r8, [rsp+38h+arg_8]
0x18000a5b1  lea     rdx, [rsp+38h+arg_10]
0x18000a5b6  mov     [rsp+38h+arg_10], ebx
0x18000a5ba  mov     [rsp+38h+arg_8], ebx
0x18000a5be  mov     rax, [rax+48h]
0x18000a5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5c7  mov     ebx, eax
0x18000a5c9  cmp     [rdi+60h], rbp
0x18000a5cd  jz      short loc_18000A628
0x18000a5cf  mov     ecx, 70h ; 'p'; cb
0x18000a5d4  call    cs:__imp_CoTaskMemAlloc
0x18000a5da  mov     rcx, rax
0x18000a5dd  test    rax, rax
0x18000a5e0  jnz     short loc_18000A5E9
0x18000a5e2  mov     ebx, 8007000Eh
0x18000a5e7  jmp     short loc_18000A628
0x18000a5e9  mov     rax, [rdi+60h]
0x18000a5ed  xor     ebx, ebx
0x18000a5ef  mov     rbp, rcx
0x18000a5f2  movups  xmm0, xmmword ptr [rax]
0x18000a5f5  movups  xmmword ptr [rcx], xmm0
0x18000a5f8  movups  xmm1, xmmword ptr [rax+10h]
0x18000a5fc  movups  xmmword ptr [rcx+10h], xmm1
0x18000a600  movups  xmm0, xmmword ptr [rax+20h]
0x18000a604  movups  xmmword ptr [rcx+20h], xmm0
0x18000a608  movups  xmm1, xmmword ptr [rax+30h]
0x18000a60c  movups  xmmword ptr [rcx+30h], xmm1
0x18000a610  movups  xmm0, xmmword ptr [rax+40h]
0x18000a614  movups  xmmword ptr [rcx+40h], xmm0
0x18000a618  movups  xmm1, xmmword ptr [rax+50h]
0x18000a61c  movups  xmmword ptr [rcx+50h], xmm1
0x18000a620  movups  xmm0, xmmword ptr [rax+60h]
0x18000a624  movups  xmmword ptr [rcx+60h], xmm0
0x18000a628  lea     rcx, ?g_csStatmonData@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a62f  call    cs:__imp_LeaveCriticalSection
0x18000a635  mov     [rsi], rbp
0x18000a638  jmp     short loc_18000A63F
0x18000a63a  mov     ebx, 80070057h
0x18000a63f  mov     eax, ebx
0x18000a641  mov     rbx, [rsp+38h+arg_0]
0x18000a646  add     rsp, 20h
0x18000a64a  pop     rdi
0x18000a64b  pop     rsi
0x18000a64c  pop     rbp
0x18000a64d  retn
```
