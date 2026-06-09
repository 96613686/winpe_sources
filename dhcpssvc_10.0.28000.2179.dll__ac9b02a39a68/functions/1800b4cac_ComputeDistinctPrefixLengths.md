# ComputeDistinctPrefixLengths

- ea: `0x1800b4cac`
- end: `0x1800b4f1b`
- name: `ComputeDistinctPrefixLengths`
- size: `623`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b3f3c`
- `0x1800b4738`
- `0x1800b546c`

## callees

- `0x18000282c`
- `0x180003228`
- `0x1800b4cac`
- `0x1800b57c0`
- `0x1800b5e24`
- `0x1800cda7a`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b4cfc`
- `ESENT!JetSetCurrentIndexA` at `0x1800b4cfc`
- `ESENT!JetMakeKey` at `0x1800b4e87`
- `ESENT!JetMakeKey` at `0x1800b4e87`
- `ESENT!JetSeek` at `0x1800b4eb3`
- `ESENT!JetSeek` at `0x1800b4eb3`
- `ESENT!JetMove` at `0x1800b4e0f`
- `ESENT!JetMove` at `0x1800b4e0f`
- `KERNEL32!EnterCriticalSection` at `0x1800b4ce3`
- `KERNEL32!EnterCriticalSection` at `0x1800b4ce3`
- `KERNEL32!LeaveCriticalSection` at `0x1800b4d53`
- `KERNEL32!LeaveCriticalSection` at `0x1800b4d53`

## string_xrefs

- `0x1800b4d0a`: `ComputeDistinctPrefixLengths:SetCurrentIndex`
- `0x1800b4ec1`: `ComputeDistinctPrefixLengths:Seek`
- `0x1800b4e95`: `ComputeDistinctPrefixLengths:MakeKey`
- `0x1800b4e1d`: `ComputeDistinctPrefixLengths:MoveFirst`

## pseudocode

```c
__int64 ComputeDistinctPrefixLengths(JET_SESID sesid, __int64 a2, __int64 a3, ...)
{
  JET_TABLEID v3; // rsi
  __int64 v5; // rbx
  unsigned int v6; // ebp
  _QWORD *v7; // rcx
  unsigned __int64 i; // rbx
  __int64 result; // rax
  unsigned int Key; // eax
  unsigned int v11; // eax
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
      v11 = JetSeek(sesid, v3, 0x10u);
      if ( (unsigned int)FilterMapJetError(v11, "ComputeDistinctPrefixLengths:Seek")
        || (unsigned int)FilterJetGetValue(sesid, v3, *(_DWORD *)(FilterGlobalTable + 56), &cbData) )
      {
        break;
      }
      DistinctWildcardPrefixLengths[v5] = pvData;
      if ( (unsigned __int64)++v5 >= 0xFF )
        goto LABEL_4;
    }
  }
  memset_0(&DistinctWildcardPrefixLengths[v5], 0, 255 - v5);
LABEL_4:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_03049d434df230c93e283a47ac7b66e1_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  for ( i = 0; i < 0xFF; ++i )
  {
    result = (unsigned __int8)DistinctWildcardPrefixLengths[i];
    if ( !(_BYTE)result )
      break;
    if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x8000) != 0 )
    {
      result = WPP_SF_D(
                 v7[2],
                 22,
                 &WPP_03049d434df230c93e283a47ac7b66e1_Traceguids,
                 (unsigned __int8)DistinctWildcardPrefixLengths[i]);
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x8000) != 0 )
    return WPP_SF_(v7[2], 23, &WPP_03049d434df230c93e283a47ac7b66e1_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800b4cac  mov     rax, rsp
0x1800b4caf  mov     [rax+8], rbx
0x1800b4cb3  mov     [rax+20h], r9
0x1800b4cb7  mov     [rax+18h], r8
0x1800b4cbb  push    rbp
0x1800b4cbc  push    rsi
0x1800b4cbd  push    rdi
0x1800b4cbe  push    r12
0x1800b4cc0  push    r13
0x1800b4cc2  sub     rsp, 30h
0x1800b4cc6  mov     rsi, cs:FilterGlobalTableHandle
0x1800b4ccd  mov     rdi, rcx
0x1800b4cd0  xor     ebx, ebx
0x1800b4cd2  mov     dword ptr [rax+18h], 1
0x1800b4cd9  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b4ce0  mov     [rax+20h], bl
0x1800b4ce3  call    cs:__imp_EnterCriticalSection
0x1800b4cea  nop     dword ptr [rax+rax+00h]
0x1800b4cef  lea     r8, szIndexName; "WildcardMatch"
0x1800b4cf6  mov     rdx, rsi; tableid
0x1800b4cf9  mov     rcx, rdi; sesid
0x1800b4cfc  call    cs:__imp_JetSetCurrentIndexA
0x1800b4d03  nop     dword ptr [rax+rax+00h]
0x1800b4d08  mov     ecx, eax
0x1800b4d0a  lea     rdx, aComputedistinc_0; "ComputeDistinctPrefixLengths:SetCurrent"...
0x1800b4d11  mov     ebp, eax
0x1800b4d13  call    FilterMapJetError
0x1800b4d18  lea     r13, DistinctWildcardPrefixLengths
0x1800b4d1f  mov     r12d, 0FFh
0x1800b4d25  test    eax, eax
0x1800b4d27  jz      loc_1800B4E00
0x1800b4d2d  lea     rdx, szIndexName; "WildcardMatch"
0x1800b4d34  mov     ecx, ebp
0x1800b4d36  call    FilterMapJetError
0x1800b4d3b  mov     r8, r12
0x1800b4d3e  lea     rcx, [rbx+r13]; void *
0x1800b4d42  sub     r8, rbx; Size
0x1800b4d45  xor     edx, edx; Val
0x1800b4d47  call    memset_0
0x1800b4d4c  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b4d53  call    cs:__imp_LeaveCriticalSection
0x1800b4d5a  nop     dword ptr [rax+rax+00h]
0x1800b4d5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4d66  lea     rsi, WPP_GLOBAL_Control
0x1800b4d6d  lea     rbp, WPP_03049d434df230c93e283a47ac7b66e1_Traceguids
0x1800b4d74  mov     edi, 8000h
0x1800b4d79  cmp     rcx, rsi
0x1800b4d7c  jz      short loc_1800B4D9B
0x1800b4d7e  test    [rcx+1Ch], edi
0x1800b4d81  jz      short loc_1800B4D9B
0x1800b4d83  mov     rcx, [rcx+10h]
0x1800b4d87  mov     edx, 15h
0x1800b4d8c  mov     r8, rbp
0x1800b4d8f  call    WPP_SF_
0x1800b4d94  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4d9b  xor     ebx, ebx
0x1800b4d9d  movzx   eax, byte ptr [rbx+r13]
0x1800b4da2  test    al, al
0x1800b4da4  jz      short loc_1800B4DD3
0x1800b4da6  cmp     rcx, rsi
0x1800b4da9  jz      short loc_1800B4DCB
0x1800b4dab  test    [rcx+1Ch], edi
0x1800b4dae  jz      short loc_1800B4DCB
0x1800b4db0  mov     rcx, [rcx+10h]
0x1800b4db4  mov     r9d, eax
0x1800b4db7  mov     edx, 16h
0x1800b4dbc  mov     r8, rbp
0x1800b4dbf  call    WPP_SF_D
0x1800b4dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4dcb  inc     rbx
0x1800b4dce  cmp     rbx, r12
0x1800b4dd1  jb      short loc_1800B4D9D
0x1800b4dd3  cmp     rcx, rsi
0x1800b4dd6  jz      short loc_1800B4DEE
0x1800b4dd8  test    [rcx+1Ch], edi
0x1800b4ddb  jz      short loc_1800B4DEE
0x1800b4ddd  mov     rcx, [rcx+10h]
0x1800b4de1  mov     edx, 17h
0x1800b4de6  mov     r8, rbp
0x1800b4de9  call    WPP_SF_
0x1800b4dee  mov     rbx, [rsp+58h+arg_0]
0x1800b4df3  add     rsp, 30h
0x1800b4df7  pop     r13
0x1800b4df9  pop     r12
0x1800b4dfb  pop     rdi
0x1800b4dfc  pop     rsi
0x1800b4dfd  pop     rbp
0x1800b4dfe  retn
0x1800b4e00  xor     r9d, r9d; grbit
0x1800b4e03  mov     r8d, 80000000h; cRow
0x1800b4e09  mov     rdx, rsi; tableid
0x1800b4e0c  mov     rcx, rdi; sesid
0x1800b4e0f  call    cs:__imp_JetMove
0x1800b4e16  nop     dword ptr [rax+rax+00h]
0x1800b4e1b  mov     ecx, eax
0x1800b4e1d  lea     rdx, aComputedistinc_1; "ComputeDistinctPrefixLengths:MoveFirst"
0x1800b4e24  mov     ebp, eax
0x1800b4e26  call    FilterMapJetError
0x1800b4e2b  test    eax, eax
0x1800b4e2d  jnz     loc_1800B4D2D
0x1800b4e33  mov     r8, cs:FilterGlobalTable
0x1800b4e3a  lea     rax, [rsp+58h+cbData]
0x1800b4e3f  lea     r9, [rsp+58h+pvData]
0x1800b4e44  mov     qword ptr [rsp+58h+grbit], rax; unsigned int *
0x1800b4e49  mov     rdx, rsi; tableid
0x1800b4e4c  mov     rcx, rdi; sesid
0x1800b4e4f  mov     r8d, [r8+38h]; columnid
0x1800b4e53  call    FilterJetGetValue
0x1800b4e58  test    eax, eax
0x1800b4e5a  jnz     loc_1800B4D3B
0x1800b4e60  mov     al, byte ptr [rsp+58h+pvData]
0x1800b4e64  mov     ebx, 1
0x1800b4e69  mov     cs:DistinctWildcardPrefixLengths, al
0x1800b4e6f  mov     r9d, [rsp+58h+cbData]; cbData
0x1800b4e74  lea     r8, [rsp+58h+pvData]; pvData
0x1800b4e79  mov     rdx, rsi; tableid
0x1800b4e7c  mov     [rsp+58h+grbit], 201h; grbit
0x1800b4e84  mov     rcx, rdi; sesid
0x1800b4e87  call    cs:__imp_JetMakeKey
0x1800b4e8e  nop     dword ptr [rax+rax+00h]
0x1800b4e93  mov     ecx, eax
0x1800b4e95  lea     rdx, aComputedistinc; "ComputeDistinctPrefixLengths:MakeKey"
0x1800b4e9c  call    FilterMapJetError
0x1800b4ea1  test    eax, eax
0x1800b4ea3  jnz     loc_1800B4D3B
0x1800b4ea9  lea     r8d, [rax+10h]; grbit
0x1800b4ead  mov     rdx, rsi; tableid
0x1800b4eb0  mov     rcx, rdi; sesid
0x1800b4eb3  call    cs:__imp_JetSeek
0x1800b4eba  nop     dword ptr [rax+rax+00h]
0x1800b4ebf  mov     ecx, eax
0x1800b4ec1  lea     rdx, aComputedistinc_2; "ComputeDistinctPrefixLengths:Seek"
0x1800b4ec8  call    FilterMapJetError
0x1800b4ecd  test    eax, eax
0x1800b4ecf  jnz     loc_1800B4D3B
0x1800b4ed5  mov     r8, cs:FilterGlobalTable
0x1800b4edc  lea     rax, [rsp+58h+cbData]
0x1800b4ee1  lea     r9, [rsp+58h+pvData]
0x1800b4ee6  mov     qword ptr [rsp+58h+grbit], rax; unsigned int *
0x1800b4eeb  mov     rdx, rsi; tableid
0x1800b4eee  mov     rcx, rdi; sesid
0x1800b4ef1  mov     r8d, [r8+38h]; columnid
0x1800b4ef5  call    FilterJetGetValue
0x1800b4efa  test    eax, eax
0x1800b4efc  jnz     loc_1800B4D3B
0x1800b4f02  mov     al, byte ptr [rsp+58h+pvData]
0x1800b4f06  mov     [rbx+r13], al
0x1800b4f0a  inc     rbx
0x1800b4f0d  cmp     rbx, r12
0x1800b4f10  jb      loc_1800B4E6F
0x1800b4f16  jmp     loc_1800B4D4C
```
