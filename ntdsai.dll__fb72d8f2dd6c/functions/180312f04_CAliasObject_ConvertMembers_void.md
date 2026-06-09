# CAliasObject::ConvertMembers(void)

- ea: `0x180312f04`
- end: `0x1803134a0`
- name: `?ConvertMembers@CAliasObject@@QEAAJXZ`
- size: `1436`
- prototype: `NTSTATUS __fastcall(CAliasObject *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1803148b0`

## callees

- `0x18001e090`
- `0x18001ea60`
- `0x180312f04`
- `0x1803aff80`
- `0x1803b0070`
- `0x1803d7370`
- `0x1803d89d4`
- `0x1803e00d0`
- `0x1803e0d10`
- `0x180453340`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803133fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180313418`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803133fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180313418`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180313208`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180313208`
- `ntdll!RtlAllocateHeap` at `0x1803131b0`
- `ntdll!RtlAllocateHeap` at `0x180313286`
- `ntdll!RtlAllocateHeap` at `0x1803131b0`
- `ntdll!RtlAllocateHeap` at `0x180313286`
- `ntdll!RtlFreeHeap` at `0x18031316f`
- `ntdll!RtlFreeHeap` at `0x18031331b`
- `ntdll!RtlFreeHeap` at `0x180313338`
- `ntdll!RtlFreeHeap` at `0x18031316f`
- `ntdll!RtlFreeHeap` at `0x18031331b`
- `ntdll!RtlFreeHeap` at `0x180313338`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180313124`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180313124`
- `ntdll!RtlInitUnicodeString` at `0x180312f8c`
- `ntdll!RtlInitUnicodeString` at `0x18031338b`
- `ntdll!RtlInitUnicodeString` at `0x180312f8c`
- `ntdll!RtlInitUnicodeString` at `0x18031338b`
- `ntdll!RtlCopySid` at `0x180312fb7`
- `ntdll!RtlCopySid` at `0x180312fb7`
- `ntdll!RtlLengthSid` at `0x180313440`
- `ntdll!RtlLengthSid` at `0x180313440`
- `SAMSRV!SampWriteEventLog` at `0x180313155`
- `SAMSRV!SampWriteEventLog` at `0x1803133bc`
- `SAMSRV!SampWriteEventLog` at `0x180313155`
- `SAMSRV!SampWriteEventLog` at `0x1803133bc`

## pseudocode

```c
NTSTATUS __fastcall CAliasObject::ConvertMembers(CAliasObject *this)
{
  const WCHAR *v2; // rdx
  void *ObjectSid; // rax
  NTSTATUS result; // eax
  int v5; // ebx
  unsigned int v6; // r15d
  __int64 v7; // rdi
  char *v8; // r14
  unsigned int v9; // r12d
  __int64 j; // rbx
  __int64 v11; // rsi
  __int64 k; // rbx
  __int64 v13; // rcx
  __int64 v14; // r14
  char *Heap; // r15
  int v16; // eax
  __int64 v17; // r14
  unsigned int v18; // ebx
  int v19; // eax
  _DWORD *v20; // rbx
  int v21; // r14d
  unsigned int v22; // r9d
  __int64 v23; // r8
  _DWORD *v24; // rcx
  char *v25; // rdx
  __int64 v26; // rax
  HLOCAL *v27; // rcx
  __int64 i; // rbx
  int m; // [rsp+30h] [rbp-D0h]
  unsigned int v30; // [rsp+34h] [rbp-CCh]
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  char *v32; // [rsp+40h] [rbp-C0h]
  __int128 v33; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  PSID Sid[500]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v37[500]; // [rsp+1020h] [rbp+F20h] BYREF
  _BYTE DestinationSid[72]; // [rsp+1FC0h] [rbp+1EC0h] BYREF

  memset_0(Sid, 0, sizeof(Sid));
  hMem = 0;
  memset_0(v37, 0, sizeof(v37));
  v2 = (const WCHAR *)*((_QWORD *)this + 18);
  UnicodeString = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v2);
  ObjectSid = (void *)SampDsGetObjectSid(*(_QWORD *)(*((_QWORD *)this + 12) + 80LL));
  if ( !ObjectSid )
    return -1073741595;
  result = RtlCopySid(0x44u, DestinationSid, ObjectSid);
  m = result;
  v5 = result;
  if ( result >= 0 )
  {
    memset_0(Sid, 0, sizeof(Sid));
    v6 = *((_DWORD *)this + 42);
    v7 = 0;
    v8 = (char *)*((_QWORD *)this + 20);
    v9 = 0;
    v30 = v6;
    v32 = v8;
    if ( v6 )
    {
      while ( 1 )
      {
        if ( v5 < 0 )
          return v5;
        Sid[v7] = v8;
        v7 = (unsigned int)(v7 + 1);
        if ( v9 == v6 - 1 || (_DWORD)v7 == 500 )
          break;
LABEL_54:
        ++v9;
        v5 = m;
        v8 += RtlLengthSid(v8);
        v32 = v8;
        if ( v9 >= v6 )
          goto LABEL_55;
      }
      if ( (int)SampMaybeBeginDsTransaction(1) < 0 )
      {
        m = -1073741801;
        LODWORD(v7) = 0;
LABEL_47:
        v27 = (HLOCAL *)hMem;
        if ( hMem )
        {
          for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
          {
            if ( v27[i] )
            {
              LocalFree(v27[i]);
              *((_QWORD *)hMem + i) = 0;
              v27 = (HLOCAL *)hMem;
            }
          }
          LocalFree(v27);
          hMem = 0;
        }
        memset_0(Sid, 0, sizeof(Sid));
        v7 = 0;
        goto LABEL_54;
      }
      if ( (int)SampDsResolveSidsForDsUpgrade((unsigned int)DestinationSid, (unsigned int)Sid, v7, 1, (__int64)&hMem) < 0 )
      {
        if ( hMem )
        {
          for ( j = 0; (unsigned int)j < (unsigned int)v7; j = (unsigned int)(j + 1) )
          {
            *(_QWORD *)&v33 = 0;
            if ( (int)SampDsResolveSidsForDsUpgrade(
                        (unsigned int)DestinationSid,
                        (unsigned int)&Sid[j],
                        1,
                        1,
                        (__int64)&v33) < 0 )
              *((_QWORD *)hMem + j) = 0;
            else
              *((_QWORD *)hMem + j) = *(_QWORD *)v33;
          }
        }
      }
      memset_0(v37, 0, sizeof(v37));
      v11 = 0;
      for ( k = 0; (unsigned int)k < (unsigned int)v7; k = (unsigned int)(k + 1) )
      {
        v13 = *((_QWORD *)hMem + k);
        if ( v13 )
        {
          v37[v11] = v13;
          v11 = (unsigned int)(v11 + 1);
        }
        else
        {
          RtlConvertSidToUnicodeString(&UnicodeString, Sid[k], 1u);
          SampWriteEventLog(SAMMSG_ERROR_ALIAS_MEMBER_UNKNOWN, L"uud", &UnicodeString, &DestinationString, 4);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UnicodeString.Buffer);
        }
      }
      v33 = 0;
      if ( (_DWORD)v11 )
      {
        v14 = *((_QWORD *)this + 10);
        Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * (unsigned int)v11);
        if ( !Heap )
        {
          m = -1073741801;
LABEL_23:
          SampMaybeEndDsTransaction(2);
          v16 = m;
          goto LABEL_24;
        }
        v20 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 24 * v11);
        if ( v20 )
        {
          v22 = 0;
          v23 = 0;
          do
          {
            v24 = (_DWORD *)v37[v23];
            ++v22;
            v25 = &Heap[16 * v23];
            *(_DWORD *)v25 = *v24;
            v26 = 3 * v23;
            *((_QWORD *)v25 + 1) = v24;
            ++v23;
            v20[2 * v26 + 2] = 1;
            v20[2 * v26] = 3;
            *(_QWORD *)&v20[2 * v26 + 4] = v25;
          }
          while ( v22 < (unsigned int)v11 );
          LODWORD(v33) = v11;
          *((_QWORD *)&v33 + 1) = v20;
          v21 = SampDsSetAttributes(v14, 67371008, 3, 3, (__int64)&v33);
        }
        else
        {
          v21 = -1073741801;
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        if ( v20 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
        m = v21;
        if ( v21 < 0 )
          goto LABEL_23;
      }
      v16 = SampMaybeEndDsTransaction(3);
      m = v16;
LABEL_24:
      if ( v16 < 0 )
      {
        v17 = 0;
        for ( m = 0; (unsigned int)v17 < (unsigned int)v11; v17 = (unsigned int)(v17 + 1) )
        {
          v18 = 0;
          while ( 1 )
          {
            if ( ++v18 > 1 )
              Sleep(1000 * v18);
            if ( (int)SampMaybeBeginDsTransaction(1) >= 0 )
            {
              m = SampDsAddMembershipAttribute(*((_QWORD *)this + 10), 0, 3, 3, v37[v17], 0);
              if ( m < 0 )
              {
                SampMaybeEndDsTransaction(2);
                v19 = m;
              }
              else
              {
                v19 = SampMaybeEndDsTransaction(3);
                m = v19;
              }
              if ( v19 >= 0 )
                break;
            }
            if ( v18 > 5 )
            {
              RtlInitUnicodeString(&UnicodeString, (PCWSTR)(v37[v17] + 56LL));
              SampWriteEventLog(SAMMSG_ERROR_ALIAS_MEMBER, L"uub", &UnicodeString, &DestinationString, 4);
              m = 0;
              break;
            }
          }
        }
      }
      v6 = v30;
      v8 = v32;
      goto LABEL_47;
    }
LABEL_55:
    if ( v5 >= 0 )
      return 0;
    else
      return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180312f04  push    rbp
0x180312f06  push    rbx
0x180312f07  push    rsi
0x180312f08  push    rdi
0x180312f09  push    r12
0x180312f0b  push    r13
0x180312f0d  push    r14
0x180312f0f  push    r15
0x180312f11  lea     rbp, [rsp-1F18h]
0x180312f19  mov     eax, 2018h
0x180312f1e  call    _alloca_probe
0x180312f23  sub     rsp, rax
0x180312f26  mov     rax, cs:__security_cookie
0x180312f2d  xor     rax, rsp
0x180312f30  mov     [rbp+1F50h+var_48], rax
0x180312f37  mov     r13, rcx
0x180312f3a  xor     edx, edx; Val
0x180312f3c  lea     rcx, [rbp+1F50h+Sid]; void *
0x180312f40  mov     r8d, 0FA0h; Size
0x180312f46  call    memset_0
0x180312f4b  xor     edx, edx; Val
0x180312f4d  mov     [rsp+2050h+hMem], 0
0x180312f56  mov     r8d, 0FA0h; Size
0x180312f5c  lea     rcx, [rbp+1F50h+var_1030]; void *
0x180312f63  call    memset_0
0x180312f68  mov     rdx, [r13+90h]; SourceString
0x180312f6f  lea     rcx, [rsp+2050h+DestinationString]; DestinationString
0x180312f74  xorps   xmm0, xmm0
0x180312f77  mov     [rsp+2050h+var_2020], 0
0x180312f7f  xorps   xmm1, xmm1
0x180312f82  movups  xmmword ptr [rsp+2050h+UnicodeString.Length], xmm0
0x180312f87  movups  xmmword ptr [rsp+2050h+DestinationString.Length], xmm1
0x180312f8c  call    cs:__imp_RtlInitUnicodeString
0x180312f92  mov     rcx, [r13+60h]
0x180312f96  mov     rcx, [rcx+50h]
0x180312f9a  call    SampDsGetObjectSid
0x180312f9f  test    rax, rax
0x180312fa2  jz      loc_180313478
0x180312fa8  mov     r8, rax; SourceSid
0x180312fab  lea     rdx, [rbp+1F50h+DestinationSid]; DestinationSid
0x180312fb2  mov     ecx, 44h ; 'D'; DestinationSidLength
0x180312fb7  call    cs:__imp_RtlCopySid
0x180312fbd  mov     [rsp+2050h+var_2020], eax
0x180312fc1  mov     ebx, eax
0x180312fc3  test    eax, eax
0x180312fc5  js      loc_18031347D
0x180312fcb  xor     edx, edx; Val
0x180312fcd  lea     rcx, [rbp+1F50h+Sid]; void *
0x180312fd1  mov     r8d, 0FA0h; Size
0x180312fd7  call    memset_0
0x180312fdc  mov     r15d, [r13+0A8h]
0x180312fe3  xor     edi, edi
0x180312fe5  mov     r14, [r13+0A0h]
0x180312fec  xor     r12d, r12d
0x180312fef  mov     [rsp+2050h+var_201C], r15d
0x180312ff4  mov     [rsp+2050h+var_2010], r14
0x180312ff9  test    r15d, r15d
0x180312ffc  jz      loc_18031345D
0x180313002  test    ebx, ebx
0x180313004  js      loc_180313461
0x18031300a  mov     [rbp+rdi*8+1F50h+Sid], r14
0x18031300f  lea     eax, [r15-1]
0x180313013  inc     edi
0x180313015  cmp     r12d, eax
0x180313018  jz      short loc_180313026
0x18031301a  cmp     edi, 1F4h
0x180313020  jnz     loc_18031343A
0x180313026  mov     ecx, 1
0x18031302b  call    SampMaybeBeginDsTransaction
0x180313030  mov     [rsp+2050h+var_2020], eax
0x180313034  test    eax, eax
0x180313036  js      loc_180313465
0x18031303c  lea     rax, [rsp+2050h+hMem]
0x180313041  mov     r14d, 1
0x180313047  mov     r9d, r14d
0x18031304a  mov     [rsp+2050h+var_2030], rax
0x18031304f  mov     r8d, edi
0x180313052  lea     rdx, [rbp+1F50h+Sid]
0x180313056  lea     rcx, [rbp+1F50h+DestinationSid]
0x18031305d  call    SampDsResolveSidsForDsUpgrade
0x180313062  mov     [rsp+2050h+var_2020], eax
0x180313066  test    eax, eax
0x180313068  jns     short loc_1803130DC
0x18031306a  cmp     [rsp+2050h+hMem], 0
0x180313070  jz      short loc_1803130DC
0x180313072  xor     ebx, ebx
0x180313074  test    edi, edi
0x180313076  jz      short loc_1803130D4
0x180313078  lea     rax, [rsp+2050h+var_2008]
0x18031307d  mov     qword ptr [rsp+2050h+var_2008], 0
0x180313086  lea     rdx, [rbp+1F50h+Sid]
0x18031308a  mov     [rsp+2050h+var_2030], rax
0x18031308f  lea     rdx, [rdx+rbx*8]
0x180313093  mov     r9d, r14d
0x180313096  mov     r8d, r14d
0x180313099  lea     rcx, [rbp+1F50h+DestinationSid]
0x1803130a0  call    SampDsResolveSidsForDsUpgrade
0x1803130a5  mov     [rsp+2050h+var_2020], eax
0x1803130a9  test    eax, eax
0x1803130ab  js      short loc_1803130C0
0x1803130ad  mov     rax, qword ptr [rsp+2050h+var_2008]
0x1803130b2  mov     rcx, [rax]
0x1803130b5  mov     rax, [rsp+2050h+hMem]
0x1803130ba  mov     [rax+rbx*8], rcx
0x1803130be  jmp     short loc_1803130CD
0x1803130c0  mov     rax, [rsp+2050h+hMem]
0x1803130c5  mov     qword ptr [rax+rbx*8], 0
0x1803130cd  add     ebx, r14d
0x1803130d0  cmp     ebx, edi
0x1803130d2  jb      short loc_180313078
0x1803130d4  mov     [rsp+2050h+var_2020], 0
0x1803130dc  xor     edx, edx; Val
0x1803130de  lea     rcx, [rbp+1F50h+var_1030]; void *
0x1803130e5  mov     r8d, 0FA0h; Size
0x1803130eb  call    memset_0
0x1803130f0  xor     esi, esi
0x1803130f2  xor     ebx, ebx
0x1803130f4  test    edi, edi
0x1803130f6  jz      loc_18031317C
0x1803130fc  mov     rax, [rsp+2050h+hMem]
0x180313101  mov     rcx, [rax+rbx*8]
0x180313105  test    rcx, rcx
0x180313108  jz      short loc_180313117
0x18031310a  mov     [rbp+rsi*8+1F50h+var_1030], rcx
0x180313112  add     esi, r14d
0x180313115  jmp     short loc_180313175
0x180313117  mov     rdx, [rbp+rbx*8+1F50h+Sid]; Sid
0x18031311c  lea     rcx, [rsp+2050h+UnicodeString]; UnicodeString
0x180313121  mov     r8b, r14b; AllocateDestinationString
0x180313124  call    cs:__imp_RtlConvertSidToUnicodeString
0x18031312a  lea     rax, [rsp+2050h+var_2020]
0x18031312f  mov     [rsp+2050h+var_2028], rax
0x180313134  lea     r9, [rsp+2050h+DestinationString]
0x180313139  lea     r8, [rsp+2050h+UnicodeString]
0x18031313e  mov     [rsp+2050h+var_2030], 4
0x180313147  lea     rdx, aUud; "uud"
0x18031314e  lea     rcx, SAMMSG_ERROR_ALIAS_MEMBER_UNKNOWN
0x180313155  call    cs:__imp_SampWriteEventLog
0x18031315b  mov     rcx, gs:60h
0x180313164  xor     edx, edx; Flags
0x180313166  mov     r8, [rsp+2050h+UnicodeString.Buffer]; P
0x18031316b  mov     rcx, [rcx+30h]; HeapHandle
0x18031316f  call    cs:__imp_RtlFreeHeap
0x180313175  add     ebx, r14d
0x180313178  cmp     ebx, edi
0x18031317a  jb      short loc_1803130FC
0x18031317c  xorps   xmm0, xmm0
0x18031317f  movups  [rsp+2050h+var_2008], xmm0
0x180313184  cmp     esi, r14d
0x180313187  jnb     short loc_180313196
0x180313189  mov     [rsp+2050h+var_2020], 0
0x180313191  jmp     loc_18031334C
0x180313196  mov     rcx, gs:60h
0x18031319f  xor     edx, edx; Flags
0x1803131a1  mov     r14, [r13+50h]
0x1803131a5  mov     r8d, esi
0x1803131a8  shl     r8, 4; Size
0x1803131ac  mov     rcx, [rcx+30h]; HeapHandle
0x1803131b0  call    cs:__imp_RtlAllocateHeap
0x1803131b6  mov     r15, rax
0x1803131b9  test    rax, rax
0x1803131bc  jnz     loc_18031326F
0x1803131c2  mov     [rsp+2050h+var_2020], 0C0000017h
0x1803131ca  mov     ecx, 2
0x1803131cf  call    SampMaybeEndDsTransaction
0x1803131d4  mov     eax, [rsp+2050h+var_2020]
0x1803131d8  test    eax, eax
0x1803131da  jns     loc_1803133D4
0x1803131e0  xor     eax, eax
0x1803131e2  xor     r14d, r14d
0x1803131e5  mov     [rsp+2050h+var_2020], eax
0x1803131e9  test    esi, esi
0x1803131eb  jz      loc_1803133D4
0x1803131f1  test    eax, eax
0x1803131f3  js      loc_1803133D4
0x1803131f9  xor     ebx, ebx
0x1803131fb  inc     ebx
0x1803131fd  cmp     ebx, 1
0x180313200  jbe     short loc_18031320E
0x180313202  imul    ecx, ebx, 3E8h; dwMilliseconds
0x180313208  call    cs:__imp_Sleep
0x18031320e  mov     ecx, 1
0x180313213  call    SampMaybeBeginDsTransaction
0x180313218  mov     [rsp+2050h+var_2020], eax
0x18031321c  test    eax, eax
0x18031321e  js      loc_180313371
0x180313224  mov     rax, [rbp+r14*8+1F50h+var_1030]
0x18031322c  xor     edx, edx
0x18031322e  mov     rcx, [r13+50h]
0x180313232  mov     [rsp+2050h+var_2028], 0
0x18031323b  mov     [rsp+2050h+var_2030], rax
0x180313240  mov     eax, 3
0x180313245  mov     r9d, eax
0x180313248  mov     r8d, eax
0x18031324b  call    SampDsAddMembershipAttribute
0x180313250  mov     [rsp+2050h+var_2020], eax
0x180313254  test    eax, eax
0x180313256  js      loc_18031335F
0x18031325c  mov     ecx, 3
0x180313261  call    SampMaybeEndDsTransaction
0x180313266  mov     [rsp+2050h+var_2020], eax
0x18031326a  jmp     loc_18031336D
0x18031326f  mov     rcx, gs:60h
0x180313278  lea     r8, [rsi+rsi*2]
0x18031327c  shl     r8, 3; Size
0x180313280  xor     edx, edx; Flags
0x180313282  mov     rcx, [rcx+30h]; HeapHandle
0x180313286  call    cs:__imp_RtlAllocateHeap
0x18031328c  mov     rbx, rax
0x18031328f  test    rax, rax
0x180313292  jnz     short loc_18031329C
0x180313294  mov     r14d, 0C0000017h
0x18031329a  jmp     short loc_180313309
0x18031329c  xor     r9d, r9d
0x18031329f  xor     r8d, r8d
0x1803132a2  mov     rcx, [rbp+r8*8+1F50h+var_1030]
0x1803132aa  mov     rdx, r8
0x1803132ad  shl     rdx, 4
0x1803132b1  inc     r9d
0x1803132b4  add     rdx, r15
0x1803132b7  mov     eax, [rcx]
0x1803132b9  mov     [rdx], eax
0x1803132bb  lea     rax, [r8+r8*2]
0x1803132bf  mov     [rdx+8], rcx
0x1803132c3  inc     r8
0x1803132c6  mov     dword ptr [rbx+rax*8+8], 1
0x1803132ce  mov     ecx, 3
0x1803132d3  mov     [rbx+rax*8], ecx
0x1803132d6  mov     [rbx+rax*8+10h], rdx
0x1803132db  cmp     r9d, esi
0x1803132de  jb      short loc_1803132A2
0x1803132e0  lea     rax, [rsp+2050h+var_2008]
0x1803132e5  mov     dword ptr [rsp+2050h+var_2008], esi
0x1803132e9  mov     r9d, ecx
0x1803132ec  mov     [rsp+2050h+var_2030], rax
0x1803132f1  mov     r8d, ecx
0x1803132f4  mov     qword ptr [rsp+2050h+var_2008+8], rbx
0x1803132f9  mov     rcx, r14
0x1803132fc  mov     edx, 4040000h
0x180313301  call    SampDsSetAttributes
0x180313306  mov     r14d, eax
0x180313309  mov     rcx, gs:60h
0x180313312  mov     r8, r15; P
0x180313315  xor     edx, edx; Flags
0x180313317  mov     rcx, [rcx+30h]; HeapHandle
0x18031331b  call    cs:__imp_RtlFreeHeap
0x180313321  test    rbx, rbx
0x180313324  jz      short loc_18031333E
0x180313326  mov     rcx, gs:60h
0x18031332f  mov     r8, rbx; P
0x180313332  xor     edx, edx; Flags
0x180313334  mov     rcx, [rcx+30h]; HeapHandle
0x180313338  call    cs:__imp_RtlFreeHeap
0x18031333e  mov     [rsp+2050h+var_2020], r14d
0x180313343  test    r14d, r14d
0x180313346  js      loc_1803131CA
0x18031334c  mov     ecx, 3
0x180313351  call    SampMaybeEndDsTransaction
0x180313356  mov     [rsp+2050h+var_2020], eax
0x18031335a  jmp     loc_1803131D8
0x18031335f  mov     ecx, 2
0x180313364  call    SampMaybeEndDsTransaction
0x180313369  mov     eax, [rsp+2050h+var_2020]
0x18031336d  test    eax, eax
0x18031336f  jns     short loc_1803133C8
0x180313371  cmp     ebx, 5
0x180313374  jbe     loc_1803131FB
0x18031337a  mov     rdx, [rbp+r14*8+1F50h+var_1030]
0x180313382  lea     rcx, [rsp+2050h+UnicodeString]; DestinationString
0x180313387  add     rdx, 38h ; '8'; SourceString
0x18031338b  call    cs:__imp_RtlInitUnicodeString
0x180313391  lea     rax, [rsp+2050h+var_2020]
0x180313396  mov     [rsp+2050h+var_2028], rax
0x18031339b  lea     r9, [rsp+2050h+DestinationString]
0x1803133a0  lea     r8, [rsp+2050h+UnicodeString]
0x1803133a5  mov     [rsp+2050h+var_2030], 4
0x1803133ae  lea     rdx, aUub; "uub"
0x1803133b5  lea     rcx, SAMMSG_ERROR_ALIAS_MEMBER
0x1803133bc  call    cs:__imp_SampWriteEventLog
0x1803133c2  xor     eax, eax
0x1803133c4  mov     [rsp+2050h+var_2020], eax
0x1803133c8  inc     r14d
0x1803133cb  cmp     r14d, esi
0x1803133ce  jb      loc_1803131F1
0x1803133d4  mov     r15d, [rsp+2050h+var_201C]
0x1803133d9  mov     r14, [rsp+2050h+var_2010]
0x1803133de  mov     rcx, [rsp+2050h+hMem]
0x1803133e3  test    rcx, rcx
0x1803133e6  jz      short loc_180313427
0x1803133e8  xor     ebx, ebx
0x1803133ea  test    edi, edi
0x1803133ec  jz      short loc_180313418
0x1803133ee  mov     rax, [rcx+rbx*8]
0x1803133f2  test    rax, rax
0x1803133f5  jz      short loc_180313412
0x1803133f7  mov     rcx, rax; hMem
0x1803133fa  call    cs:__imp_LocalFree
0x180313400  mov     rax, [rsp+2050h+hMem]
0x180313405  mov     qword ptr [rax+rbx*8], 0
0x18031340d  mov     rcx, [rsp+2050h+hMem]; hMem
  ... truncated ...
```
