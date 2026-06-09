# OneXAddSqmRecord

- ea: `0x18001f690`
- end: `0x18001f986`
- name: `OneXAddSqmRecord`
- size: `758`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18002a22c`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x18001f690`
- `0x18001f98c`
- `0x180020250`
- `0x180020aea`
- `0x1800214f0`
- `0x18002be44`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x18001f7f8`
- `ntdll!WinSqmAddToStreamEx` at `0x18001f7f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001f85f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001f85f`
- `MobileNetworking!ReleaseReadLock` at `0x18001f74e`
- `MobileNetworking!ReleaseReadLock` at `0x18001f74e`
- `MobileNetworking!AcquireReadLock` at `0x18001f722`
- `MobileNetworking!AcquireReadLock` at `0x18001f722`
- `MobileNetworking!ReleaseWriteLock` at `0x18001f90f`
- `MobileNetworking!ReleaseWriteLock` at `0x18001f90f`
- `MobileNetworking!AcquireWriteLock` at `0x18001f8b5`
- `MobileNetworking!AcquireWriteLock` at `0x18001f8b5`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x18001f80c`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x18001f80c`
- `MobileNetworking!FreeMemory` at `0x18001f930`
- `MobileNetworking!FreeMemory` at `0x18001f930`

## pseudocode

```c
__int64 __fastcall OneXAddSqmRecord(__int64 a1, __int64 a2)
{
  unsigned int v2; // r14d
  unsigned int v4; // esi
  unsigned int v5; // ebx
  __int64 *v6; // rax
  int v7; // eax
  unsigned int v8; // eax
  __int64 v9; // rbx
  __int64 *v10; // rcx
  __int64 v11; // rax
  __int64 result; // rax
  _QWORD v13[2]; // [rsp+30h] [rbp-89h] BYREF
  _DWORD v14[40]; // [rsp+40h] [rbp-79h] BYREF

  v2 = *(_DWORD *)(a1 + 20);
  v4 = 0;
  memset_0(v14, 0, sizeof(v14));
  v13[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 90, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids);
  OneXpRemoveExpiredSqmRecords();
  if ( !(unsigned int)OneXpFindSimilarSqmRecord(a2) )
  {
    v5 = 0;
    AcquireReadLock(qword_18003DE28);
    v6 = (__int64 *)qword_18003DE18;
    while ( v6 != &qword_18003DE18 )
    {
      v6 = (__int64 *)*v6;
      ++v5;
    }
    ReleaseReadLock(qword_18003DE28);
    if ( v5 < 0x14 )
    {
      v14[22] = *(unsigned __int8 *)(a2 + 16);
      v14[30] = *(_DWORD *)(a2 + 28);
      v14[34] = *(_DWORD *)(a2 + 20);
      v14[38] = *(_DWORD *)(a2 + 24);
      v14[26] = *(_DWORD *)(a2 + 32);
      v14[18] = *(_DWORD *)(a2 + 36);
      v14[6] = *(_DWORD *)(a2 + 40);
      v14[10] = *(_DWORD *)(a2 + 44);
      v7 = *(_DWORD *)(a2 + 48);
      v14[20] = 16;
      v14[28] = 16;
      v14[32] = 16;
      v14[36] = 16;
      v14[24] = 16;
      v14[16] = 16;
      v14[4] = 16;
      v14[8] = 16;
      v14[12] = 16;
      v14[0] = 16;
      v14[14] = v7;
      v14[2] = *(_DWORD *)(a2 + 52);
      v14[21] = 1;
      v14[29] = 1;
      v14[33] = 1;
      v14[37] = 1;
      v14[25] = 1;
      v14[17] = 1;
      v14[5] = 1;
      v14[9] = 1;
      v14[13] = 1;
      v14[1] = 1;
      WinSqmAddToStreamEx(0, 3642, 10, v14, 0);
      v8 = AllocateAndCopyPointerData(v13, a2, 64);
      v4 = v8;
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 91, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v2, v8);
      }
      else
      {
        v9 = v13[0];
        *(_DWORD *)(v9 + 56) = GetTickCount();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            92,
            WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids,
            *(unsigned int *)(a2 + 56));
        AcquireWriteLock(g_OneXInfo, qword_18003DE28, "OneXAddSqmRecord", 916);
        v10 = (__int64 *)qword_18003DE20;
        if ( *(__int64 **)qword_18003DE20 != &qword_18003DE18 )
          __fastfail(3u);
        v11 = v13[0];
        *(_QWORD *)v13[0] = &qword_18003DE18;
        *(_QWORD *)(v11 + 8) = v10;
        *v10 = v11;
        qword_18003DE20 = v11;
        v13[0] = 0;
        ReleaseWriteLock(g_OneXInfo, qword_18003DE28, "OneXAddSqmRecord", 921);
      }
    }
  }
  result = FreeMemory(v13, "OneXAddSqmRecord", 926);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    return WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 93, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v4);
  return result;
}

```

## disassembly

```asm
0x18001f690  mov     [rsp-8+arg_10], rbx
0x18001f695  push    rbp
0x18001f696  push    rsi
0x18001f697  push    rdi
0x18001f698  push    r12
0x18001f69a  push    r14
0x18001f69c  lea     rbp, [rsp-37h]
0x18001f6a1  sub     rsp, 0F0h
0x18001f6a8  mov     rax, cs:__security_cookie
0x18001f6af  xor     rax, rsp
0x18001f6b2  mov     [rbp+57h+var_30], rax
0x18001f6b6  mov     r14d, [rcx+14h]
0x18001f6ba  mov     rdi, rdx
0x18001f6bd  xor     edx, edx; Val
0x18001f6bf  lea     rcx, [rbp+57h+var_D0]; void *
0x18001f6c3  xor     esi, esi
0x18001f6c5  mov     r8d, 0A0h; Size
0x18001f6cb  call    memset_0
0x18001f6d0  mov     [rsp+110h+var_E0], rsi
0x18001f6d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6dc  lea     rax, WPP_GLOBAL_Control
0x18001f6e3  cmp     rcx, rax
0x18001f6e6  jz      short loc_18001F704
0x18001f6e8  test    dword ptr [rcx+44h], 800h
0x18001f6ef  jz      short loc_18001F704
0x18001f6f1  mov     rcx, [rcx+38h]
0x18001f6f5  lea     edx, [rsi+5Ah]
0x18001f6f8  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18001f6ff  call    WPP_SF_
0x18001f704  call    OneXpRemoveExpiredSqmRecords
0x18001f709  mov     rcx, rdi
0x18001f70c  call    OneXpFindSimilarSqmRecord
0x18001f711  test    eax, eax
0x18001f713  jnz     loc_18001F917
0x18001f719  xor     ebx, ebx
0x18001f71b  lea     rcx, qword_18003DE28
0x18001f722  call    cs:__imp_AcquireReadLock
0x18001f728  mov     rax, cs:qword_18003DE18
0x18001f72f  lea     rcx, qword_18003DE18
0x18001f736  lea     r12d, [rbx+1]
0x18001f73a  jmp     short loc_18001F742
0x18001f73c  mov     rax, [rax]
0x18001f73f  add     ebx, r12d
0x18001f742  cmp     rax, rcx
0x18001f745  jnz     short loc_18001F73C
0x18001f747  lea     rcx, qword_18003DE28
0x18001f74e  call    cs:__imp_ReleaseReadLock
0x18001f754  cmp     ebx, 14h
0x18001f757  jnb     loc_18001F917
0x18001f75d  movzx   eax, byte ptr [rdi+10h]
0x18001f761  lea     r9, [rbp+57h+var_D0]
0x18001f765  mov     ecx, 10h
0x18001f76a  mov     [rbp+57h+var_78], eax
0x18001f76d  mov     eax, [rdi+1Ch]
0x18001f770  mov     edx, 0E3Ah
0x18001f775  mov     [rbp+57h+var_58], eax
0x18001f778  mov     eax, [rdi+14h]
0x18001f77b  mov     [rbp+57h+var_48], eax
0x18001f77e  mov     eax, [rdi+18h]
0x18001f781  mov     [rbp+57h+var_38], eax
0x18001f784  mov     eax, [rdi+20h]
0x18001f787  mov     [rbp+57h+var_68], eax
0x18001f78a  mov     eax, [rdi+24h]
0x18001f78d  mov     [rbp+57h+var_88], eax
0x18001f790  mov     eax, [rdi+28h]
0x18001f793  mov     [rbp+57h+var_B8], eax
0x18001f796  mov     eax, [rdi+2Ch]
0x18001f799  mov     [rbp+57h+var_A8], eax
0x18001f79c  mov     eax, [rdi+30h]
0x18001f79f  mov     [rbp+57h+var_80], ecx
0x18001f7a2  mov     [rbp+57h+var_60], ecx
0x18001f7a5  mov     [rbp+57h+var_50], ecx
0x18001f7a8  mov     [rbp+57h+var_40], ecx
0x18001f7ab  mov     [rbp+57h+var_70], ecx
0x18001f7ae  mov     [rbp+57h+var_90], ecx
0x18001f7b1  mov     [rbp+57h+var_C0], ecx
0x18001f7b4  mov     [rbp+57h+var_B0], ecx
0x18001f7b7  mov     [rbp+57h+var_A0], ecx
0x18001f7ba  mov     [rbp+57h+var_D0], ecx
0x18001f7bd  xor     ecx, ecx
0x18001f7bf  mov     [rbp+57h+var_98], eax
0x18001f7c2  mov     eax, [rdi+34h]
0x18001f7c5  mov     [rbp+57h+var_C8], eax
0x18001f7c8  lea     r8d, [rcx+0Ah]
0x18001f7cc  mov     [rbp+57h+var_7C], r12d
0x18001f7d0  mov     [rbp+57h+var_5C], r12d
0x18001f7d4  mov     [rbp+57h+var_4C], r12d
0x18001f7d8  mov     [rbp+57h+var_3C], r12d
0x18001f7dc  mov     [rbp+57h+var_6C], r12d
0x18001f7e0  mov     [rbp+57h+var_8C], r12d
0x18001f7e4  mov     [rbp+57h+var_BC], r12d
0x18001f7e8  mov     [rbp+57h+var_AC], r12d
0x18001f7ec  mov     [rbp+57h+var_9C], r12d
0x18001f7f0  mov     [rbp+57h+var_CC], r12d
0x18001f7f4  mov     [rsp+110h+var_F0], esi
0x18001f7f8  call    cs:__imp_WinSqmAddToStreamEx
0x18001f7fe  mov     r8d, 40h ; '@'
0x18001f804  lea     rcx, [rsp+110h+var_E0]
0x18001f809  mov     rdx, rdi
0x18001f80c  call    cs:__imp_AllocateAndCopyPointerData
0x18001f812  mov     esi, eax
0x18001f814  test    eax, eax
0x18001f816  jz      short loc_18001F85A
0x18001f818  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f81f  lea     rbx, WPP_GLOBAL_Control
0x18001f826  cmp     rcx, rbx
0x18001f829  jz      loc_18001F91E
0x18001f82f  test    [rcx+44h], r12b
0x18001f833  jz      loc_18001F91E
0x18001f839  mov     rcx, [rcx+38h]
0x18001f83d  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18001f844  mov     edx, 5Bh ; '['
0x18001f849  mov     [rsp+110h+var_F0], eax
0x18001f84d  mov     r9d, r14d
0x18001f850  call    WPP_SF_dd
0x18001f855  jmp     loc_18001F91E
0x18001f85a  mov     rbx, [rsp+110h+var_E0]
0x18001f85f  call    cs:__imp_GetTickCount
0x18001f865  mov     [rbx+38h], eax
0x18001f868  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f86f  lea     rbx, WPP_GLOBAL_Control
0x18001f876  cmp     rcx, rbx
0x18001f879  jz      short loc_18001F89A
0x18001f87b  test    byte ptr [rcx+44h], 4
0x18001f87f  jz      short loc_18001F89A
0x18001f881  mov     r9d, [rdi+38h]
0x18001f885  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18001f88c  mov     rcx, [rcx+38h]
0x18001f890  mov     edx, 5Ch ; '\'
0x18001f895  call    WPP_SF_d
0x18001f89a  mov     r9d, 394h
0x18001f8a0  lea     r8, aOnexaddsqmreco; "OneXAddSqmRecord"
0x18001f8a7  lea     rdx, qword_18003DE28
0x18001f8ae  lea     rcx, g_OneXInfo
0x18001f8b5  call    cs:__imp_AcquireWriteLock
0x18001f8bb  mov     rcx, cs:qword_18003DE20
0x18001f8c2  lea     rdx, qword_18003DE18
0x18001f8c9  cmp     [rcx], rdx
0x18001f8cc  jz      short loc_18001F8D5
0x18001f8ce  mov     ecx, 3
0x18001f8d3  int     29h; Win8: RtlFailFast(ecx)
0x18001f8d5  mov     rax, [rsp+110h+var_E0]
0x18001f8da  lea     r8, aOnexaddsqmreco; "OneXAddSqmRecord"
0x18001f8e1  mov     r9d, 399h
0x18001f8e7  mov     [rax], rdx
0x18001f8ea  lea     rdx, qword_18003DE28
0x18001f8f1  mov     [rax+8], rcx
0x18001f8f5  mov     [rcx], rax
0x18001f8f8  lea     rcx, g_OneXInfo
0x18001f8ff  mov     cs:qword_18003DE20, rax
0x18001f906  mov     [rsp+110h+var_E0], 0
0x18001f90f  call    cs:__imp_ReleaseWriteLock
0x18001f915  jmp     short loc_18001F91E
0x18001f917  lea     rbx, WPP_GLOBAL_Control
0x18001f91e  mov     r8d, 39Eh
0x18001f924  lea     rdx, aOnexaddsqmreco; "OneXAddSqmRecord"
0x18001f92b  lea     rcx, [rsp+110h+var_E0]
0x18001f930  call    cs:__imp_FreeMemory
0x18001f936  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f93d  cmp     rcx, rbx
0x18001f940  jz      short loc_18001F963
0x18001f942  test    dword ptr [rcx+44h], 800h
0x18001f949  jz      short loc_18001F963
0x18001f94b  mov     rcx, [rcx+38h]
0x18001f94f  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18001f956  mov     edx, 5Dh ; ']'
0x18001f95b  mov     r9d, esi
0x18001f95e  call    WPP_SF_D
0x18001f963  mov     rcx, [rbp+57h+var_30]
0x18001f967  xor     rcx, rsp; StackCookie
0x18001f96a  call    __security_check_cookie
0x18001f96f  mov     rbx, [rsp+110h+arg_10]
0x18001f977  add     rsp, 0F0h
0x18001f97e  pop     r14
0x18001f980  pop     r12
0x18001f982  pop     rdi
0x18001f983  pop     rsi
0x18001f984  pop     rbp
0x18001f985  retn
```
