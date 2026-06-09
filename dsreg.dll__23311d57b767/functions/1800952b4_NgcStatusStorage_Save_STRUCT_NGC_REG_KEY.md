# NgcStatusStorage::Save(STRUCT_NGC_REG_KEY)

- ea: `0x1800952b4`
- end: `0x1800954a0`
- name: `?Save@NgcStatusStorage@@QEAAJUSTRUCT_NGC_REG_KEY@@@Z`
- size: `492`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180080674`
- `0x1800834f4`

## callees

- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x180012cf0`
- `0x18001c02c`
- `0x18001e010`
- `0x18003334c`
- `0x180044300`
- `0x180094db4`
- `0x1800952b4`
- `0x1800954a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095379`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180095385`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180095385`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009536f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009536f`
- `RPCRT4!UuidCompare` at `0x18009532b`
- `RPCRT4!UuidCompare` at `0x18009532b`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::Save(__int64 a1, __int64 a2)
{
  const WCHAR *v2; // rbx
  __int128 v4; // xmm7
  int v5; // esi
  UUID v6; // xmm6
  int v7; // r14d
  int v8; // r15d
  NgcStatusStorage *v9; // rcx
  int v10; // eax
  void *v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  struct STRUCT_NGC_REG_KEY *v15; // r8
  int v16; // eax
  RPC_STATUS Status; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v18[4]; // [rsp+40h] [rbp-C8h] BYREF
  int v19; // [rsp+60h] [rbp-A8h]
  int v20; // [rsp+64h] [rbp-A4h]
  int v21; // [rsp+68h] [rbp-A0h]
  _BYTE v22[28]; // [rsp+6Ch] [rbp-9Ch]
  _BYTE v23[28]; // [rsp+ACh] [rbp-5Ch]
  UUID Uuid2; // [rsp+C8h] [rbp-40h] BYREF
  PCNZWCH lpString2; // [rsp+D8h] [rbp-30h]
  int v26; // [rsp+E0h] [rbp-28h]
  int v27; // [rsp+E4h] [rbp-24h]
  int v28; // [rsp+E8h] [rbp-20h]
  UUID Uuid1; // [rsp+108h] [rbp+0h] BYREF

  v2 = *(const WCHAR **)(a2 + 16);
  v4 = *(_OWORD *)(a2 + 48);
  v5 = *(_DWORD *)(a2 + 24);
  v6 = *(UUID *)a2;
  v7 = *(_DWORD *)(a2 + 28);
  v8 = *(_DWORD *)(a2 + 32);
  *(_OWORD *)v23 = *(_OWORD *)(a2 + 36);
  Status = 0;
  *(_OWORD *)&v23[12] = v4;
  NgcStatusStorage::GetKey(a1, &Uuid2);
  Uuid1 = v6;
  if ( UuidCompare(&Uuid1, &Uuid2, &Status) || v7 != v27 || v5 != v26 || v8 != v28 )
    goto LABEL_11;
  if ( v2 == lpString2 )
  {
LABEL_15:
    Logger::TraceVerbose(
      (wchar_t *)L"%s: The given status is identical to the current status. No need to save...",
      L"NgcStatusStorage::Save");
    return 0;
  }
  if ( !v2 || !lpString2 )
    goto LABEL_11;
  v10 = CompareStringW(0x7Fu, 0, v2, -1, lpString2, -1);
  if ( v10 )
  {
    if ( v10 != 2 )
      goto LABEL_11;
    goto LABEL_15;
  }
  if ( GetLastError() )
    SetLastError(0);
LABEL_11:
  if ( *(_QWORD *)(a1 + 8) )
  {
    NgcStatusStorage::Cleanup(v9, *(struct STRUCT_NGC_REG_KEY **)a1);
LABEL_17:
    v15 = *(struct STRUCT_NGC_REG_KEY **)a1;
    *(UUID *)&v18[1] = v6;
    v18[3] = v2;
    *(_OWORD *)v22 = *(_OWORD *)v23;
    v19 = v5;
    *(_OWORD *)&v22[12] = v4;
    v20 = v7;
    v21 = v8;
    v16 = NgcStatusStorage::Duplicate(v12, &v18[1], v15);
    v13 = v16;
    if ( v16 >= 0 )
    {
      *(_QWORD *)(a1 + 8) = 1;
      v13 = NgcStatusStorage::Save((NgcStatusStorage *)a1);
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"NgcStatusStorage::Save",
        L"StringDup",
        (unsigned int)v16);
    }
    goto LABEL_20;
  }
  SafeFree(*(void **)a1);
  v11 = SafeAlloc(0x40u);
  *(_QWORD *)a1 = v11;
  if ( v11 )
    goto LABEL_17;
  v13 = -2147024882;
  Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"NgcStatusStorage::Save");
LABEL_20:
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"NgcStatusStorage::Save", v13);
  return v13;
}

```

## disassembly

```asm
0x1800952b4  mov     rax, rsp
0x1800952b7  mov     [rax+18h], rbx
0x1800952bb  push    rbp
0x1800952bc  push    rsi
0x1800952bd  push    rdi
0x1800952be  push    r14
0x1800952c0  push    r15
0x1800952c2  lea     rbp, [rax-68h]
0x1800952c6  sub     rsp, 140h
0x1800952cd  movaps  xmmword ptr [rax-38h], xmm6
0x1800952d1  movaps  xmmword ptr [rax-48h], xmm7
0x1800952d5  mov     rax, cs:__security_cookie
0x1800952dc  xor     rax, rsp
0x1800952df  mov     [rbp+60h+var_50], rax
0x1800952e3  movups  xmm0, xmmword ptr [rdx+24h]
0x1800952e7  mov     rbx, [rdx+10h]
0x1800952eb  mov     rdi, rcx
0x1800952ee  movups  xmm7, xmmword ptr [rdx+30h]
0x1800952f2  mov     esi, [rdx+18h]
0x1800952f5  movaps  xmm6, xmmword ptr [rdx]
0x1800952f8  mov     r14d, [rdx+1Ch]
0x1800952fc  mov     r15d, [rdx+20h]
0x180095300  lea     rdx, [rbp+60h+Uuid2]
0x180095304  movups  xmmword ptr [rbp+60h+var_BC], xmm0
0x180095308  mov     [rsp+160h+Status], 0
0x180095310  movaps  xmmword ptr [rbp+60h+var_BC+0Ch], xmm7
0x180095314  call    ?GetKey@NgcStatusStorage@@QEAA?AUSTRUCT_NGC_REG_KEY@@XZ; NgcStatusStorage::GetKey(void)
0x180095319  lea     r8, [rsp+160h+Status]; Status
0x18009531e  lea     rdx, [rbp+60h+Uuid2]; Uuid2
0x180095322  lea     rcx, [rbp+60h+Uuid1]; Uuid1
0x180095326  movdqu  xmmword ptr [rbp+60h+Uuid1.Data1], xmm6
0x18009532b  call    cs:__imp_UuidCompare
0x180095331  test    eax, eax
0x180095333  jnz     short loc_18009538B
0x180095335  cmp     r14d, [rbp+60h+var_84]
0x180095339  jnz     short loc_18009538B
0x18009533b  cmp     esi, [rbp+60h+var_88]
0x18009533e  jnz     short loc_18009538B
0x180095340  cmp     r15d, [rbp+60h+var_80]
0x180095344  jnz     short loc_18009538B
0x180095346  mov     rax, [rbp+60h+var_90]
0x18009534a  cmp     rbx, rax
0x18009534d  jz      short loc_1800953CE
0x18009534f  test    rbx, rbx
0x180095352  jz      short loc_18009538B
0x180095354  test    rax, rax
0x180095357  jz      short loc_18009538B
0x180095359  xor     edx, edx; dwCmpFlags
0x18009535b  or      r9d, 0FFFFFFFFh; cchCount1
0x18009535f  mov     [rsp+160h+cchCount2], r9d; cchCount2
0x180095364  mov     r8, rbx; lpString1
0x180095367  mov     [rsp+160h+lpString2], rax; lpString2
0x18009536c  lea     ecx, [rdx+7Fh]; Locale
0x18009536f  call    cs:__imp_CompareStringW
0x180095375  test    eax, eax
0x180095377  jnz     short loc_1800953C9
0x180095379  call    cs:__imp_GetLastError
0x18009537f  test    eax, eax
0x180095381  jz      short loc_18009538B
0x180095383  xor     ecx, ecx; dwErrCode
0x180095385  call    cs:__imp_SetLastError
0x18009538b  cmp     qword ptr [rdi+8], 0
0x180095390  jnz     short loc_1800953E8
0x180095392  mov     rcx, [rdi]; lpMem
0x180095395  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18009539a  mov     ecx, 40h ; '@'; unsigned __int64
0x18009539f  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x1800953a4  mov     [rdi], rax
0x1800953a7  test    rax, rax
0x1800953aa  jnz     short loc_1800953F0
0x1800953ac  lea     rdx, aNgcstatusstora_9; "NgcStatusStorage::Save"
0x1800953b3  mov     ebx, 8007000Eh
0x1800953b8  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800953bf  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800953c4  jmp     loc_18009545B
0x1800953c9  cmp     eax, 2
0x1800953cc  jnz     short loc_18009538B
0x1800953ce  lea     rdx, aNgcstatusstora_9; "NgcStatusStorage::Save"
0x1800953d5  lea     rcx, aSTheGivenStatu; "%s: The given status is identical to th"...
0x1800953dc  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800953e1  xor     eax, eax
0x1800953e3  jmp     loc_180095473
0x1800953e8  mov     rdx, [rdi]; struct STRUCT_NGC_REG_KEY *
0x1800953eb  call    ?Cleanup@NgcStatusStorage@@AEAAXPEAUSTRUCT_NGC_REG_KEY@@@Z; NgcStatusStorage::Cleanup(STRUCT_NGC_REG_KEY *)
0x1800953f0  movups  xmm0, xmmword ptr [rbp+60h+var_BC]
0x1800953f4  mov     r8, [rdi]
0x1800953f7  lea     rdx, [rsp+160h+var_128+8]
0x1800953fc  movdqu  xmmword ptr [rsp+160h+var_128+8], xmm6
0x180095402  mov     [rsp+160h+var_110], rbx
0x180095407  movups  [rsp+160h+var_104+8], xmm0
0x18009540c  mov     [rsp+160h+var_108], esi
0x180095410  movups  [rsp+160h+var_F0], xmm7
0x180095415  mov     dword ptr [rsp+160h+var_104], r14d
0x18009541a  mov     dword ptr [rsp+160h+var_104+4], r15d
0x18009541f  call    ?Duplicate@NgcStatusStorage@@AEAAJUSTRUCT_NGC_REG_KEY@@PEAU2@@Z; NgcStatusStorage::Duplicate(STRUCT_NGC_REG_KEY,STRUCT_NGC_REG_KEY *)
0x180095424  mov     ebx, eax
0x180095426  test    eax, eax
0x180095428  jns     short loc_180095449
0x18009542a  mov     r9d, eax
0x18009542d  lea     r8, aStringdup; "StringDup"
0x180095434  lea     rdx, aNgcstatusstora_9; "NgcStatusStorage::Save"
0x18009543b  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180095442  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095447  jmp     short loc_18009545B
0x180095449  mov     rcx, rdi; this
0x18009544c  mov     qword ptr [rdi+8], 1
0x180095454  call    ?Save@NgcStatusStorage@@QEAAJXZ; NgcStatusStorage::Save(void)
0x180095459  mov     ebx, eax
0x18009545b  mov     r8d, ebx
0x18009545e  lea     rdx, aNgcstatusstora_9; "NgcStatusStorage::Save"
0x180095465  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18009546c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180095471  mov     eax, ebx
0x180095473  mov     rcx, [rbp+60h+var_50]
0x180095477  xor     rcx, rsp; StackCookie
0x18009547a  call    __security_check_cookie
0x18009547f  lea     r11, [rsp+160h+var_20]
0x180095487  mov     rbx, [r11+40h]
0x18009548b  movaps  xmm6, xmmword ptr [r11-10h]
0x180095490  movaps  xmm7, xmmword ptr [r11-20h]
0x180095495  mov     rsp, r11
0x180095498  pop     r15
0x18009549a  pop     r14
0x18009549c  pop     rdi
0x18009549d  pop     rsi
0x18009549e  pop     rbp
0x18009549f  retn
```
