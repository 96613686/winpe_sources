# DeleteMMPolicy

- ea: `0x18001a860`
- end: `0x18001aa43`
- name: `DeleteMMPolicy`
- size: `483`
- prototype: `__int64 __fastcall(__int64, __int64, _WORD *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180004770`
- `0x180011010`
- `0x180027758`
- `0x1800277f8`

## callees

- `0x18000e510`
- `0x180019d80`
- `0x180019df8`
- `0x180019e74`
- `0x18001a7c8`
- `0x18001a860`
- `0x18001acdc`
- `0x180044af4`
- `0x18004d090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a8a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a8a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a971`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a9e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a971`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a9e3`

## pseudocode

```c
__int64 __fastcall DeleteMMPolicy(__int64 a1, __int64 a2, _WORD *a3)
{
  __int64 v4; // rcx
  __int64 MMPolicy; // rax
  _QWORD *v6; // rsi
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned int v11; // eax
  __int128 v13; // [rsp+30h] [rbp-58h] BYREF

  v13 = 0;
  if ( !a3 || !*a3 )
    return 87;
  EnterCriticalSection(&gcSPDSection);
  MMPolicy = FindMMPolicy(v4, a3);
  v6 = (_QWORD *)MMPolicy;
  if ( !MMPolicy )
  {
    v7 = 13004;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_17;
    v9 = 37;
    goto LABEL_7;
  }
  v13 = *(_OWORD *)MMPolicy;
  if ( *(_DWORD *)(MMPolicy + 24) )
  {
    v7 = 13005;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_17;
    v9 = 38;
LABEL_7:
    v10 = v7;
LABEL_16:
    WPP_SF_d(v8[2], v9, WPP_3b22585727a234aeebb3c3c9670a017a_Traceguids, v10);
LABEL_17:
    LeaveCriticalSection(&gcSPDSection);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_S_guid_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          (unsigned int)WPP_3b22585727a234aeebb3c3c9670a017a_Traceguids,
          v6[2],
          (__int64)v6,
          v7);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)WPP_3b22585727a234aeebb3c3c9670a017a_Traceguids,
        (_DWORD)a3,
        v7);
    }
    return v7;
  }
  LipsApiIkePolicyDelete(MMPolicy);
  v11 = DeleteIniMMPolicy(v6);
  v7 = v11;
  if ( v11 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_17;
    v9 = 39;
    v10 = v11;
    goto LABEL_16;
  }
  LeaveCriticalSection(&gcSPDSection);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S_guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      (unsigned int)WPP_3b22585727a234aeebb3c3c9670a017a_Traceguids,
      (_DWORD)a3,
      (__int64)&v13);
  return 0;
}

```

## disassembly

```asm
0x18001a860  push    rbx
0x18001a862  push    rbp
0x18001a863  push    rsi
0x18001a864  push    rdi
0x18001a865  push    r12
0x18001a867  push    r14
0x18001a869  sub     rsp, 58h
0x18001a86d  mov     rax, cs:__security_cookie
0x18001a874  xor     rax, rsp
0x18001a877  mov     [rsp+88h+var_48], rax
0x18001a87c  xor     r14d, r14d
0x18001a87f  xorps   xmm0, xmm0
0x18001a882  mov     rbp, r8
0x18001a885  movups  [rsp+88h+var_58], xmm0
0x18001a88a  test    r8, r8
0x18001a88d  jz      loc_18001AA24
0x18001a893  cmp     [r8], r14w
0x18001a897  jz      loc_18001AA24
0x18001a89d  lea     rcx, gcSPDSection; lpCriticalSection
0x18001a8a4  call    cs:__imp_EnterCriticalSection
0x18001a8aa  mov     rdx, rbp
0x18001a8ad  call    FindMMPolicy
0x18001a8b2  lea     r12, WPP_3b22585727a234aeebb3c3c9670a017a_Traceguids
0x18001a8b9  mov     rsi, rax
0x18001a8bc  test    rax, rax
0x18001a8bf  jnz     short loc_18001A8EF
0x18001a8c1  mov     edi, 32CCh
0x18001a8c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8cd  lea     rbx, WPP_GLOBAL_Control
0x18001a8d4  cmp     rcx, rbx
0x18001a8d7  jz      loc_18001A96A
0x18001a8dd  test    byte ptr [rcx+1Ch], 10h
0x18001a8e1  jz      loc_18001A96A
0x18001a8e7  lea     edx, [rax+25h]
0x18001a8ea  mov     r9d, edi
0x18001a8ed  jmp     short loc_18001A95E
0x18001a8ef  movups  xmm0, xmmword ptr [rax]
0x18001a8f2  movdqu  [rsp+88h+var_58], xmm0
0x18001a8f8  cmp     [rax+18h], r14d
0x18001a8fc  jz      short loc_18001A923
0x18001a8fe  mov     edi, 32CDh
0x18001a903  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a90a  lea     rbx, WPP_GLOBAL_Control
0x18001a911  cmp     rcx, rbx
0x18001a914  jz      short loc_18001A96A
0x18001a916  test    byte ptr [rcx+1Ch], 10h
0x18001a91a  jz      short loc_18001A96A
0x18001a91c  mov     edx, 26h ; '&'
0x18001a921  jmp     short loc_18001A8EA
0x18001a923  mov     rcx, rsi
0x18001a926  call    LipsApiIkePolicyDelete
0x18001a92b  mov     rcx, rsi; lpMem
0x18001a92e  call    DeleteIniMMPolicy
0x18001a933  mov     edi, eax
0x18001a935  test    eax, eax
0x18001a937  jz      loc_18001A9DC
0x18001a93d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a944  lea     rbx, WPP_GLOBAL_Control
0x18001a94b  cmp     rcx, rbx
0x18001a94e  jz      short loc_18001A96A
0x18001a950  test    byte ptr [rcx+1Ch], 10h
0x18001a954  jz      short loc_18001A96A
0x18001a956  mov     edx, 27h ; '''
0x18001a95b  mov     r9d, eax
0x18001a95e  mov     rcx, [rcx+10h]
0x18001a962  mov     r8, r12
0x18001a965  call    WPP_SF_d
0x18001a96a  lea     rcx, gcSPDSection; lpCriticalSection
0x18001a971  call    cs:__imp_LeaveCriticalSection
0x18001a977  test    rsi, rsi
0x18001a97a  jz      short loc_18001A9AE
0x18001a97c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a983  cmp     rcx, rbx
0x18001a986  jz      short loc_18001A9D8
0x18001a988  test    byte ptr [rcx+1Ch], 10h
0x18001a98c  jz      short loc_18001A9D8
0x18001a98e  mov     r9, [rsi+10h]
0x18001a992  mov     edx, 29h ; ')'
0x18001a997  mov     rcx, [rcx+10h]
0x18001a99b  mov     r8, r12
0x18001a99e  mov     [rsp+88h+var_60], edi
0x18001a9a2  mov     [rsp+88h+var_68], rsi
0x18001a9a7  call    WPP_SF_S_guid_D
0x18001a9ac  jmp     short loc_18001A9D8
0x18001a9ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9b5  cmp     rcx, rbx
0x18001a9b8  jz      short loc_18001A9D8
0x18001a9ba  test    byte ptr [rcx+1Ch], 10h
0x18001a9be  jz      short loc_18001A9D8
0x18001a9c0  mov     rcx, [rcx+10h]
0x18001a9c4  mov     edx, 2Ah ; '*'
0x18001a9c9  mov     r9, rbp
0x18001a9cc  mov     dword ptr [rsp+88h+var_68], edi
0x18001a9d0  mov     r8, r12
0x18001a9d3  call    WPP_SF_SD
0x18001a9d8  mov     eax, edi
0x18001a9da  jmp     short loc_18001AA29
0x18001a9dc  lea     rcx, gcSPDSection; lpCriticalSection
0x18001a9e3  call    cs:__imp_LeaveCriticalSection
0x18001a9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9f0  lea     rbx, WPP_GLOBAL_Control
0x18001a9f7  cmp     rcx, rbx
0x18001a9fa  jz      short loc_18001AA20
0x18001a9fc  test    byte ptr [rcx+1Ch], 4
0x18001aa00  jz      short loc_18001AA20
0x18001aa02  mov     rcx, [rcx+10h]
0x18001aa06  lea     rax, [rsp+88h+var_58]
0x18001aa0b  mov     edx, 28h ; '('
0x18001aa10  mov     [rsp+88h+var_68], rax
0x18001aa15  mov     r9, rbp
0x18001aa18  mov     r8, r12
0x18001aa1b  call    WPP_SF_S_guid_
0x18001aa20  xor     eax, eax
0x18001aa22  jmp     short loc_18001AA29
0x18001aa24  mov     eax, 57h ; 'W'
0x18001aa29  mov     rcx, [rsp+88h+var_48]
0x18001aa2e  xor     rcx, rsp; StackCookie
0x18001aa31  call    __security_check_cookie
0x18001aa36  add     rsp, 58h
0x18001aa3a  pop     r14
0x18001aa3c  pop     r12
0x18001aa3e  pop     rdi
0x18001aa3f  pop     rsi
0x18001aa40  pop     rbp
0x18001aa41  pop     rbx
0x18001aa42  retn
```
