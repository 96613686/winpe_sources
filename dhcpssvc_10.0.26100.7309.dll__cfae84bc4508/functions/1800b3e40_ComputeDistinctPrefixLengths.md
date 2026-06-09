# ComputeDistinctPrefixLengths

- ea: `0x1800b3e40`
- end: `0x1800b40a0`
- name: `ComputeDistinctPrefixLengths`
- size: `608`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b30e0`
- `0x1800b38c8`
- `0x1800b45f0`

## callees

- `0x180002854`
- `0x18000323c`
- `0x1800b3e40`
- `0x1800b4944`
- `0x1800b4f88`
- `0x1800cc99a`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b3e90`
- `ESENT!JetSetCurrentIndexA` at `0x1800b3e90`
- `ESENT!JetMakeKey` at `0x1800b3f53`
- `ESENT!JetMakeKey` at `0x1800b3f53`
- `ESENT!JetSeek` at `0x1800b3f7b`
- `ESENT!JetSeek` at `0x1800b3f7b`
- `ESENT!JetMove` at `0x1800b3edf`
- `ESENT!JetMove` at `0x1800b3edf`
- `KERNEL32!EnterCriticalSection` at `0x1800b3e77`
- `KERNEL32!EnterCriticalSection` at `0x1800b3e77`
- `KERNEL32!LeaveCriticalSection` at `0x1800b3ff3`
- `KERNEL32!LeaveCriticalSection` at `0x1800b3ff3`

## string_xrefs

- `0x1800b3eed`: `ComputeDistinctPrefixLengths:MoveFirst`
- `0x1800b3f61`: `ComputeDistinctPrefixLengths:MakeKey`
- `0x1800b3e9e`: `ComputeDistinctPrefixLengths:SetCurrentIndex`
- `0x1800b3f89`: `ComputeDistinctPrefixLengths:Seek`

## pseudocode

```c
__int64 ComputeDistinctPrefixLengths(JET_SESID sesid, __int64 a2, __int64 a3, ...)
{
  JET_TABLEID v3; // rsi
  unsigned __int64 v5; // rbx
  unsigned int v6; // ebp
  unsigned int Key; // eax
  unsigned int v8; // eax
  _QWORD *v9; // rcx
  unsigned __int64 i; // rbx
  __int64 result; // rax
  unsigned int cbData; // [rsp+70h] [rbp+18h] BYREF
  int v13; // [rsp+74h] [rbp+1Ch]
  __int64 pvData; // [rsp+78h] [rbp+20h] BYREF
  va_list pvDataa; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(pvDataa, a3);
  pvData = va_arg(va1, _QWORD);
  v13 = HIDWORD(a3);
  v3 = FilterGlobalTableHandle;
  v5 = 0;
  cbData = 1;
  LOBYTE(pvData) = 0;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v6 = JetSetCurrentIndexA(sesid, v3, "WildcardMatch");
  if ( (unsigned int)FilterMapJetError(v6, "ComputeDistinctPrefixLengths:SetCurrentIndex")
    || (v6 = JetMove(sesid, v3, 0x80000000, 0),
        (unsigned int)FilterMapJetError(v6, "ComputeDistinctPrefixLengths:MoveFirst")) )
  {
    FilterMapJetError(v6, "WildcardMatch");
  }
  else if ( !(unsigned int)FilterJetGetValue(sesid, v3, *(_DWORD *)(FilterGlobalTable + 56), &cbData) )
  {
    v5 = 1;
    DistinctWildcardPrefixLengths[0] = pvData;
    while ( 1 )
    {
      Key = JetMakeKey(sesid, v3, pvDataa, cbData, 0x201u);
      if ( (unsigned int)FilterMapJetError(Key, "ComputeDistinctPrefixLengths:MakeKey") )
        break;
      v8 = JetSeek(sesid, v3, 0x10u);
      if ( !(unsigned int)FilterMapJetError(v8, "ComputeDistinctPrefixLengths:Seek")
        && !(unsigned int)FilterJetGetValue(sesid, v3, *(_DWORD *)(FilterGlobalTable + 56), &cbData) )
      {
        DistinctWildcardPrefixLengths[v5] = pvData;
        if ( ++v5 < 0xFF )
          continue;
      }
      if ( v5 >= 0xFF )
        goto LABEL_12;
      break;
    }
  }
  memset_0(&DistinctWildcardPrefixLengths[v5], 0, 255 - v5);
LABEL_12:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_03049d434df230c93e283a47ac7b66e1_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  for ( i = 0; i < 0xFF; ++i )
  {
    result = (unsigned __int8)DistinctWildcardPrefixLengths[i];
    if ( !(_BYTE)result )
      break;
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x8000) != 0 )
    {
      result = WPP_SF_D(
                 v9[2],
                 22,
                 &WPP_03049d434df230c93e283a47ac7b66e1_Traceguids,
                 (unsigned __int8)DistinctWildcardPrefixLengths[i]);
      v9 = WPP_GLOBAL_Control;
    }
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x8000) != 0 )
    return WPP_SF_(v9[2], 23, &WPP_03049d434df230c93e283a47ac7b66e1_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800b3e40  mov     rax, rsp
0x1800b3e43  mov     [rax+8], rbx
0x1800b3e47  mov     [rax+20h], r9
0x1800b3e4b  mov     [rax+18h], r8
0x1800b3e4f  push    rbp
0x1800b3e50  push    rsi
0x1800b3e51  push    rdi
0x1800b3e52  push    r13
0x1800b3e54  push    r14
0x1800b3e56  sub     rsp, 30h
0x1800b3e5a  mov     rsi, cs:FilterGlobalTableHandle
0x1800b3e61  mov     rdi, rcx
0x1800b3e64  xor     ebx, ebx
0x1800b3e66  mov     dword ptr [rax+18h], 1
0x1800b3e6d  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b3e74  mov     [rax+20h], bl
0x1800b3e77  call    cs:__imp_EnterCriticalSection
0x1800b3e7e  nop     dword ptr [rax+rax+00h]
0x1800b3e83  lea     r8, szIndexName; "WildcardMatch"
0x1800b3e8a  mov     rdx, rsi; tableid
0x1800b3e8d  mov     rcx, rdi; sesid
0x1800b3e90  call    cs:__imp_JetSetCurrentIndexA
0x1800b3e97  nop     dword ptr [rax+rax+00h]
0x1800b3e9c  mov     ecx, eax
0x1800b3e9e  lea     rdx, aComputedistinc_0; "ComputeDistinctPrefixLengths:SetCurrent"...
0x1800b3ea5  mov     ebp, eax
0x1800b3ea7  call    FilterMapJetError
0x1800b3eac  lea     r13, DistinctWildcardPrefixLengths
0x1800b3eb3  mov     r14d, 0FFh
0x1800b3eb9  test    eax, eax
0x1800b3ebb  jz      short loc_1800B3ED0
0x1800b3ebd  lea     rdx, szIndexName; "WildcardMatch"
0x1800b3ec4  mov     ecx, ebp
0x1800b3ec6  call    FilterMapJetError
0x1800b3ecb  jmp     loc_1800B3FDB
0x1800b3ed0  xor     r9d, r9d; grbit
0x1800b3ed3  mov     r8d, 80000000h; cRow
0x1800b3ed9  mov     rdx, rsi; tableid
0x1800b3edc  mov     rcx, rdi; sesid
0x1800b3edf  call    cs:__imp_JetMove
0x1800b3ee6  nop     dword ptr [rax+rax+00h]
0x1800b3eeb  mov     ecx, eax
0x1800b3eed  lea     rdx, aComputedistinc_1; "ComputeDistinctPrefixLengths:MoveFirst"
0x1800b3ef4  mov     ebp, eax
0x1800b3ef6  call    FilterMapJetError
0x1800b3efb  test    eax, eax
0x1800b3efd  jnz     short loc_1800B3EBD
0x1800b3eff  mov     r8, cs:FilterGlobalTable
0x1800b3f06  lea     rax, [rsp+58h+cbData]
0x1800b3f0b  lea     r9, [rsp+58h+pvData]
0x1800b3f10  mov     qword ptr [rsp+58h+grbit], rax; unsigned int *
0x1800b3f15  mov     rdx, rsi; tableid
0x1800b3f18  mov     rcx, rdi; sesid
0x1800b3f1b  mov     r8d, [r8+38h]; columnid
0x1800b3f1f  call    FilterJetGetValue
0x1800b3f24  test    eax, eax
0x1800b3f26  jnz     loc_1800B3FDB
0x1800b3f2c  mov     al, byte ptr [rsp+58h+pvData]
0x1800b3f30  mov     ebx, 1
0x1800b3f35  mov     cs:DistinctWildcardPrefixLengths, al
0x1800b3f3b  mov     r9d, [rsp+58h+cbData]; cbData
0x1800b3f40  lea     r8, [rsp+58h+pvData]; pvData
0x1800b3f45  mov     rdx, rsi; tableid
0x1800b3f48  mov     [rsp+58h+grbit], 201h; grbit
0x1800b3f50  mov     rcx, rdi; sesid
0x1800b3f53  call    cs:__imp_JetMakeKey
0x1800b3f5a  nop     dword ptr [rax+rax+00h]
0x1800b3f5f  mov     ecx, eax
0x1800b3f61  lea     rdx, aComputedistinc; "ComputeDistinctPrefixLengths:MakeKey"
0x1800b3f68  call    FilterMapJetError
0x1800b3f6d  test    eax, eax
0x1800b3f6f  jnz     short loc_1800B3FDB
0x1800b3f71  lea     r8d, [rax+10h]; grbit
0x1800b3f75  mov     rdx, rsi; tableid
0x1800b3f78  mov     rcx, rdi; sesid
0x1800b3f7b  call    cs:__imp_JetSeek
0x1800b3f82  nop     dword ptr [rax+rax+00h]
0x1800b3f87  mov     ecx, eax
0x1800b3f89  lea     rdx, aComputedistinc_2; "ComputeDistinctPrefixLengths:Seek"
0x1800b3f90  call    FilterMapJetError
0x1800b3f95  test    eax, eax
0x1800b3f97  jnz     short loc_1800B3FD6
0x1800b3f99  mov     r8, cs:FilterGlobalTable
0x1800b3fa0  lea     rax, [rsp+58h+cbData]
0x1800b3fa5  lea     r9, [rsp+58h+pvData]
0x1800b3faa  mov     qword ptr [rsp+58h+grbit], rax; unsigned int *
0x1800b3faf  mov     rdx, rsi; tableid
0x1800b3fb2  mov     rcx, rdi; sesid
0x1800b3fb5  mov     r8d, [r8+38h]; columnid
0x1800b3fb9  call    FilterJetGetValue
0x1800b3fbe  test    eax, eax
0x1800b3fc0  jnz     short loc_1800B3FD6
0x1800b3fc2  mov     al, byte ptr [rsp+58h+pvData]
0x1800b3fc6  mov     [rbx+r13], al
0x1800b3fca  inc     rbx
0x1800b3fcd  cmp     rbx, r14
0x1800b3fd0  jb      loc_1800B3F3B
0x1800b3fd6  cmp     rbx, r14
0x1800b3fd9  jnb     short loc_1800B3FEC
0x1800b3fdb  mov     r8, r14
0x1800b3fde  lea     rcx, [rbx+r13]; void *
0x1800b3fe2  sub     r8, rbx; Size
0x1800b3fe5  xor     edx, edx; Val
0x1800b3fe7  call    memset_0
0x1800b3fec  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b3ff3  call    cs:__imp_LeaveCriticalSection
0x1800b3ffa  nop     dword ptr [rax+rax+00h]
0x1800b3fff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4006  lea     rsi, WPP_GLOBAL_Control
0x1800b400d  lea     rbp, WPP_03049d434df230c93e283a47ac7b66e1_Traceguids
0x1800b4014  mov     edi, 8000h
0x1800b4019  cmp     rcx, rsi
0x1800b401c  jz      short loc_1800B403B
0x1800b401e  test    [rcx+1Ch], edi
0x1800b4021  jz      short loc_1800B403B
0x1800b4023  mov     rcx, [rcx+10h]
0x1800b4027  mov     edx, 15h
0x1800b402c  mov     r8, rbp
0x1800b402f  call    WPP_SF_
0x1800b4034  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b403b  xor     ebx, ebx
0x1800b403d  movzx   eax, byte ptr [rbx+r13]
0x1800b4042  test    al, al
0x1800b4044  jz      short loc_1800B4073
0x1800b4046  cmp     rcx, rsi
0x1800b4049  jz      short loc_1800B406B
0x1800b404b  test    [rcx+1Ch], edi
0x1800b404e  jz      short loc_1800B406B
0x1800b4050  mov     rcx, [rcx+10h]
0x1800b4054  mov     r9d, eax
0x1800b4057  mov     edx, 16h
0x1800b405c  mov     r8, rbp
0x1800b405f  call    WPP_SF_D
0x1800b4064  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b406b  inc     rbx
0x1800b406e  cmp     rbx, r14
0x1800b4071  jb      short loc_1800B403D
0x1800b4073  cmp     rcx, rsi
0x1800b4076  jz      short loc_1800B408E
0x1800b4078  test    [rcx+1Ch], edi
0x1800b407b  jz      short loc_1800B408E
0x1800b407d  mov     rcx, [rcx+10h]
0x1800b4081  mov     edx, 17h
0x1800b4086  mov     r8, rbp
0x1800b4089  call    WPP_SF_
0x1800b408e  mov     rbx, [rsp+58h+arg_0]
0x1800b4093  add     rsp, 30h
0x1800b4097  pop     r14
0x1800b4099  pop     r13
0x1800b409b  pop     rdi
0x1800b409c  pop     rsi
0x1800b409d  pop     rbp
0x1800b409e  retn
```
