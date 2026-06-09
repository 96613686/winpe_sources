# CCtfServerPort::ProcessConnectionRequest(_PORT_MESSAGE *)

- ea: `0x18004004c`
- end: `0x18004044a`
- name: `?ProcessConnectionRequest@CCtfServerPort@@AEAAJPEAU_PORT_MESSAGE@@@Z`
- size: `1022`
- prototype: `__int64 __fastcall(CCtfServerPort *__hidden this, struct _PORT_MESSAGE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180040760`

## callees

- `0x18003f3e4`
- `0x18004004c`
- `0x180040450`
- `0x1800429e8`
- `0x1800743d4`
- `0x18008f874`
- `0x18009eaea`
- `0x180106a60`

## import_xrefs

- `ntdll!NtClose` at `0x180040267`
- `ntdll!NtClose` at `0x1800402c3`
- `ntdll!NtClose` at `0x180040267`
- `ntdll!NtClose` at `0x1800402c3`
- `ntdll!NtAlpcOpenSenderProcess` at `0x1800400d6`
- `ntdll!NtAlpcOpenSenderProcess` at `0x1800400d6`
- `ntdll!NtAlpcAcceptConnectPort` at `0x1800402ae`
- `ntdll!NtAlpcAcceptConnectPort` at `0x1800403e3`
- `ntdll!NtAlpcAcceptConnectPort` at `0x1800402ae`
- `ntdll!NtAlpcAcceptConnectPort` at `0x1800403e3`
- `ntdll!NtQueryInformationProcess` at `0x1800400fd`
- `ntdll!NtQueryInformationProcess` at `0x1800400fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004033d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004033d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800401d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004036f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800401d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004036f`
- `USER32!GetWindowThreadProcessId` at `0x18004019d`
- `USER32!GetWindowThreadProcessId` at `0x18004019d`

## pseudocode

```c
__int64 __fastcall CCtfServerPort::ProcessConnectionRequest(CCtfServerPort *this, struct _PORT_MESSAGE *a2)
{
  __int64 v4; // rdx
  struct CCtfServerPort::ClientInfo *v6; // rdi
  __int64 v7; // r14
  NTSTATUS v8; // r12d
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __m128i v11; // xmm2
  union _PORT_MESSAGE::$C6BC508B531A81D74C33985719C23F49 v12; // xmm6
  int v13; // r13d
  __int64 v14; // rbx
  int v15; // ebx
  struct CCtfServerPort::ClientInfo *v16; // rax
  HANDLE v17; // rcx
  __int64 result; // rax
  __int64 v19; // r8
  __int64 v20; // rdx
  HANDLE CurrentProcess; // rax
  CCtfServerPort *v22; // rcx
  CCtfServerPort *v23; // rcx
  unsigned int IntegrityLevel; // ebx
  CCtfServerPort::ImeServerInfo *v25; // rax
  __int64 v26; // rdx
  __int64 i; // rcx
  int v28; // [rsp+48h] [rbp-C0h]
  HANDLE Handle; // [rsp+58h] [rbp-B0h] BYREF
  __int64 ProcessInformation; // [rsp+60h] [rbp-A8h] BYREF
  HANDLE ProcessHandle; // [rsp+68h] [rbp-A0h] BYREF
  ULONG Length; // [rsp+70h] [rbp-98h]
  unsigned int v33; // [rsp+74h] [rbp-94h]
  struct CCtfServerPort::ClientInfo *v34; // [rsp+78h] [rbp-90h] BYREF
  DWORD dwProcessId[2]; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v36[4]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v37; // [rsp+A8h] [rbp-60h]
  __int128 v38; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v39; // [rsp+C8h] [rbp-40h]
  __m128i v40; // [rsp+D8h] [rbp-30h]
  union _PORT_MESSAGE::$C6BC508B531A81D74C33985719C23F49 v41; // [rsp+E8h] [rbp-20h]
  int v42; // [rsp+F8h] [rbp-10h]

  v36[0] = 48;
  Handle = 0;
  v34 = 0;
  v4 = *(_QWORD *)this;
  ProcessHandle = 0;
  v6 = 0;
  LODWORD(ProcessInformation) = 0;
  v7 = 0;
  memset(&v36[1], 0, 24);
  v37 = 0;
  v8 = NtAlpcOpenSenderProcess(&ProcessHandle, v4, a2, 0, 4096, v36);
  if ( v8 >= 0 )
  {
    v8 = NtQueryInformationProcess(ProcessHandle, ProcessSessionInformation, &ProcessInformation, 4u, 0);
    if ( v8 >= 0 && (_DWORD)ProcessInformation == NtCurrentPeb()->SessionId && a2->u1.s1.TotalLength == 64 )
    {
      v9 = *(_OWORD *)&a2->u1.s1.DataLength;
      Length = a2[1].u1.Length;
      v10 = *(__int128 *)((char *)&a2->8 + 8);
      v11 = *(__m128i *)&a2->ClientViewSize;
      v12 = a2[1].8;
      v38 = v9;
      v39 = v10;
      v40 = v11;
      v41 = v12;
      if ( Length == LODWORD(a2->DoNotUseThisField) )
      {
        v13 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 12));
        if ( v13 == *((_DWORD *)&a2->DoNotUseThisField + 2) )
        {
          *(_QWORD *)dwProcessId = 0;
          v33 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v12, 8));
          v14 = v33;
          GetWindowThreadProcessId((HWND)v33, dwProcessId);
          if ( !v14 || *(HANDLE *)dwProcessId == a2->ClientId.UniqueProcess )
          {
            v15 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v12, 4));
            if ( (v15 & 0x40000000) != 0 )
            {
              CurrentProcess = GetCurrentProcess();
              IntegrityLevel = CCtfServerPort::GetIntegrityLevel(v22, CurrentProcess);
              if ( !IntegrityLevel
                || (unsigned int)CCtfServerPort::GetIntegrityLevel(v23, ProcessHandle) < IntegrityLevel )
              {
                goto LABEL_15;
              }
              v25 = (CCtfServerPort::ImeServerInfo *)LocalAlloc(0x40u, 0xB0u);
              if ( v25 )
                v7 = CCtfServerPort::ImeServerInfo::ImeServerInfo(v25, (const struct MsgConnect *)&v38);
              v6 = (struct CCtfServerPort::ClientInfo *)v7;
            }
            else
            {
              v16 = (struct CCtfServerPort::ClientInfo *)LocalAlloc(0x40u, 0x58u);
              v6 = v16;
              if ( v16 )
              {
                *((_DWORD *)v16 + 7) = v15;
                *(_QWORD *)v16 = &CCtfServerPort::ClientInfo::`vftable';
                *((_DWORD *)v16 + 4) = Length;
                *((_DWORD *)v16 + 12) = v33;
                *((_QWORD *)v16 + 1) = 0;
                *((_DWORD *)v16 + 5) = v13;
                *((_DWORD *)v16 + 6) = LODWORD(v12.DoNotUseThisField);
                *((_DWORD *)v16 + 8) = 2;
                *((_DWORD *)v16 + 9) = 524289;
                *((_QWORD *)v16 + 5) = 0;
                *((_QWORD *)v16 + 7) = &CStructArray<char>::`vftable';
                *((_QWORD *)v16 + 9) = 0;
                *((_QWORD *)v16 + 8) = 0;
                *((_DWORD *)v16 + 20) = 1;
              }
              else
              {
                v6 = 0;
              }
            }
            v34 = v6;
            if ( v6 && !CCtfServerPort::AddClient(this, v6) )
            {
              CCtfServerPort::ClientInfo::Release(v6);
              v6 = 0;
              v34 = 0;
            }
          }
        }
      }
    }
  }
LABEL_15:
  if ( ProcessHandle )
    NtClose(ProcessHandle);
  if ( v6 )
  {
    memset_0(&v38, 0, 0x48u);
    v26 = *(_QWORD *)this;
    *(_QWORD *)&v39 = 512;
    LODWORD(v38) = 0x80000;
    v42 = 16;
    v8 = NtAlpcAcceptConnectPort(&Handle, v26, 0, 0, &v38, v6, a2, 0, 1);
  }
  if ( v8 >= 0 && Handle )
  {
    *((_QWORD *)v6 + 1) = Handle;
    if ( v7 )
    {
      v19 = *((_QWORD *)this + 14);
      v20 = v7 + 88;
      if ( v19 )
      {
        for ( i = v7 & -(__int64)(v20 != 0); *(_QWORD *)(i + 88); i = *(_QWORD *)(i + 88) )
          ;
        *(_QWORD *)(i + 88) = v19;
        *(_QWORD *)(*((_QWORD *)this + 14) + 96LL) = i;
      }
      *((_QWORD *)this + 14) = v7 & -(__int64)(v20 != 0);
      *((_BYTE *)this + 120) = 0;
    }
LABEL_24:
    result = 0;
    if ( Handle )
      return result;
    return 2147500037LL;
  }
  if ( v6 )
    CCtfServerPort::RemoveClient(this, &v34);
  LOBYTE(v28) = 0;
  NtAlpcAcceptConnectPort(&Handle, *(_QWORD *)this, 0, 0, 0, 0, a2, 0, v28);
  v17 = Handle;
  if ( Handle )
  {
    Handle = 0;
    NtClose(v17);
    goto LABEL_24;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18004004c  mov     rax, rsp
0x18004004f  mov     [rax+18h], rbx
0x180040053  push    rbp
0x180040054  push    rsi
0x180040055  push    rdi
0x180040056  push    r12
0x180040058  push    r13
0x18004005a  push    r14
0x18004005c  push    r15
0x18004005e  lea     rbp, [rax-58h]
0x180040062  sub     rsp, 120h
0x180040069  movaps  xmmword ptr [rax-48h], xmm6
0x18004006d  mov     rax, cs:__security_cookie
0x180040074  xor     rax, rsp
0x180040077  mov     [rbp+50h+var_50], rax
0x18004007b  xor     ebx, ebx
0x18004007d  mov     [rbp+50h+var_D0], 30h ; '0'
0x180040085  mov     r15, rdx
0x180040088  mov     [rsp+150h+Handle], rbx
0x18004008d  lea     rax, [rbp+50h+var_D0]
0x180040091  mov     [rsp+150h+var_E0], rbx
0x180040096  mov     r8, rdx
0x180040099  mov     [rsp+150h+var_128], rax
0x18004009e  mov     rdx, [rcx]
0x1800400a1  mov     rsi, rcx
0x1800400a4  xorps   xmm0, xmm0
0x1800400a7  mov     dword ptr [rsp+150h+ReturnLength], 1000h
0x1800400af  lea     rcx, [rsp+150h+ProcessHandle]
0x1800400b4  mov     [rsp+150h+ProcessHandle], rbx
0x1800400b9  xor     r9d, r9d
0x1800400bc  mov     [rbp+50h+var_B8], rbx
0x1800400c0  mov     edi, ebx
0x1800400c2  mov     dword ptr [rsp+150h+ProcessInformation], ebx
0x1800400c6  mov     r14d, ebx
0x1800400c9  mov     [rbp+50h+var_C8], rbx
0x1800400cd  mov     [rbp+50h+var_C0], rbx
0x1800400d1  movdqu  [rbp+50h+var_B0], xmm0
0x1800400d6  call    cs:__imp_NtAlpcOpenSenderProcess
0x1800400dc  mov     r12d, eax
0x1800400df  test    eax, eax
0x1800400e1  js      loc_18004025B
0x1800400e7  mov     rcx, [rsp+150h+ProcessHandle]; ProcessHandle
0x1800400ec  lea     r9d, [rbx+4]; ProcessInformationLength
0x1800400f0  lea     r8, [rsp+150h+ProcessInformation]; ProcessInformation
0x1800400f5  mov     [rsp+150h+ReturnLength], rbx; ReturnLength
0x1800400fa  lea     edx, [rbx+18h]; ProcessInformationClass
0x1800400fd  call    cs:__imp_NtQueryInformationProcess
0x180040103  mov     r12d, eax
0x180040106  test    eax, eax
0x180040108  js      loc_18004025B
0x18004010e  mov     rax, gs:60h
0x180040117  mov     ecx, [rax+2C0h]
0x18004011d  cmp     dword ptr [rsp+150h+ProcessInformation], ecx
0x180040121  jnz     loc_18004025B
0x180040127  lea     eax, [rbx+40h]
0x18004012a  cmp     [r15+2], ax
0x18004012f  jnz     loc_18004025B
0x180040135  mov     eax, [r15+28h]
0x180040139  movups  xmm0, xmmword ptr [r15]
0x18004013d  mov     dword ptr [rsp+150h+var_E8], eax
0x180040141  movups  xmm1, xmmword ptr [r15+10h]
0x180040146  movups  xmm2, xmmword ptr [r15+20h]
0x18004014b  movups  xmm6, xmmword ptr [r15+30h]
0x180040150  movaps  [rbp+50h+var_A0], xmm0
0x180040154  movaps  [rbp+50h+var_90], xmm1
0x180040158  movaps  [rbp+50h+var_80], xmm2
0x18004015c  movaps  [rbp+50h+var_70], xmm6
0x180040160  cmp     eax, [r15+8]
0x180040164  jnz     loc_18004025B
0x18004016a  psrldq  xmm2, 0Ch
0x18004016f  movd    r13d, xmm2
0x180040174  cmp     r13d, [r15+10h]
0x180040178  jnz     loc_18004025B
0x18004017e  movdqa  xmm0, xmm6
0x180040182  mov     qword ptr [rsp+150h+dwProcessId], rbx
0x180040187  psrldq  xmm0, 8
0x18004018c  lea     rdx, [rsp+150h+dwProcessId]; lpdwProcessId
0x180040191  movd    eax, xmm0
0x180040195  mov     ecx, eax; hWnd
0x180040197  mov     dword ptr [rsp+150h+var_E8+4], eax
0x18004019b  mov     ebx, eax
0x18004019d  call    cs:__imp_GetWindowThreadProcessId
0x1800401a3  test    rbx, rbx
0x1800401a6  jz      short loc_1800401B7
0x1800401a8  mov     rax, [r15+8]
0x1800401ac  cmp     qword ptr [rsp+150h+dwProcessId], rax
0x1800401b1  jnz     loc_18004025B
0x1800401b7  movdqa  xmm0, xmm6
0x1800401bb  psrldq  xmm0, 4
0x1800401c0  movd    ebx, xmm0
0x1800401c4  bt      ebx, 1Eh
0x1800401c8  jb      loc_18004033D
0x1800401ce  mov     edx, 58h ; 'X'; uBytes
0x1800401d3  lea     ecx, [rdx-18h]; uFlags
0x1800401d6  call    cs:__imp_LocalAlloc
0x1800401dc  mov     rdi, rax
0x1800401df  test    rax, rax
0x1800401e2  jz      loc_1800403F1
0x1800401e8  mov     [rdi+1Ch], ebx
0x1800401eb  lea     rax, ??_7ClientInfo@CCtfServerPort@@6B@; const CCtfServerPort::ClientInfo::`vftable'
0x1800401f2  mov     [rdi], rax
0x1800401f5  xor     ebx, ebx
0x1800401f7  mov     eax, dword ptr [rsp+150h+var_E8]
0x1800401fb  mov     [rdi+10h], eax
0x1800401fe  mov     eax, dword ptr [rsp+150h+var_E8+4]
0x180040202  mov     [rdi+30h], eax
0x180040205  lea     rax, ??_7?$CStructArray@D@@6B@; const CStructArray<char>::`vftable'
0x18004020c  mov     [rdi+8], r14
0x180040210  mov     [rdi+14h], r13d
0x180040214  movss   dword ptr [rdi+18h], xmm6
0x180040219  mov     dword ptr [rdi+20h], 2
0x180040220  mov     dword ptr [rdi+24h], 80001h
0x180040227  mov     [rdi+28h], rbx
0x18004022b  mov     [rdi+38h], rax
0x18004022f  mov     [rdi+48h], rbx
0x180040233  mov     [rdi+40h], rbx
0x180040237  mov     dword ptr [rdi+50h], 1
0x18004023e  mov     [rsp+150h+var_E0], rdi
0x180040243  test    rdi, rdi
0x180040246  jz      short loc_18004025B
0x180040248  mov     rdx, rdi; struct CCtfServerPort::ClientInfo *
0x18004024b  mov     rcx, rsi; this
0x18004024e  call    ?AddClient@CCtfServerPort@@AEAA_NPEAUClientInfo@1@@Z; CCtfServerPort::AddClient(CCtfServerPort::ClientInfo *)
0x180040253  test    al, al
0x180040255  jz      loc_1800403FA
0x18004025b  mov     rcx, [rsp+150h+ProcessHandle]; Handle
0x180040260  xor     ebx, ebx
0x180040262  test    rcx, rcx
0x180040265  jz      short loc_18004026D
0x180040267  call    cs:__imp_NtClose
0x18004026d  test    rdi, rdi
0x180040270  jnz     loc_180040393
0x180040276  test    r12d, r12d
0x180040279  jns     loc_180040303
0x18004027f  test    rdi, rdi
0x180040282  jnz     loc_180040438
0x180040288  mov     rdx, [rsi]
0x18004028b  lea     rcx, [rsp+150h+Handle]
0x180040290  mov     byte ptr [rsp+150h+var_110], bl
0x180040294  xor     r9d, r9d
0x180040297  mov     qword ptr [rsp+150h+var_118], rbx
0x18004029c  xor     r8d, r8d
0x18004029f  mov     [rsp+150h+var_120], r15
0x1800402a4  mov     [rsp+150h+var_128], rbx
0x1800402a9  mov     [rsp+150h+ReturnLength], rbx
0x1800402ae  call    cs:__imp_NtAlpcAcceptConnectPort
0x1800402b4  mov     rcx, [rsp+150h+Handle]; Handle
0x1800402b9  test    rcx, rcx
0x1800402bc  jz      short loc_1800402D2
0x1800402be  mov     [rsp+150h+Handle], rbx
0x1800402c3  call    cs:__imp_NtClose
0x1800402c9  mov     eax, ebx
0x1800402cb  cmp     [rsp+150h+Handle], rbx
0x1800402d0  jnz     short loc_1800402D7
0x1800402d2  mov     eax, 80004005h
0x1800402d7  mov     rcx, [rbp+50h+var_50]
0x1800402db  xor     rcx, rsp; StackCookie
0x1800402de  call    __security_check_cookie
0x1800402e3  lea     r11, [rsp+150h+var_30]
0x1800402eb  mov     rbx, [r11+50h]
0x1800402ef  movaps  xmm6, xmmword ptr [r11-10h]
0x1800402f4  mov     rsp, r11
0x1800402f7  pop     r15
0x1800402f9  pop     r14
0x1800402fb  pop     r13
0x1800402fd  pop     r12
0x1800402ff  pop     rdi
0x180040300  pop     rsi
0x180040301  pop     rbp
0x180040302  retn
0x180040303  mov     rax, [rsp+150h+Handle]
0x180040308  test    rax, rax
0x18004030b  jz      loc_18004027F
0x180040311  mov     [rdi+8], rax
0x180040315  test    r14, r14
0x180040318  jz      short loc_1800402C9
0x18004031a  mov     r8, [rsi+70h]
0x18004031e  lea     rdx, [r14+58h]
0x180040322  test    r8, r8
0x180040325  jnz     loc_18004040F
0x18004032b  neg     rdx
0x18004032e  sbb     rax, rax
0x180040331  and     rax, r14
0x180040334  mov     [rsi+70h], rax
0x180040338  mov     [rsi+78h], bl
0x18004033b  jmp     short loc_1800402C9
0x18004033d  call    cs:__imp_GetCurrentProcess
0x180040343  mov     rdx, rax; void *
0x180040346  call    ?GetIntegrityLevel@CCtfServerPort@@AEAAKPEAX@Z; CCtfServerPort::GetIntegrityLevel(void *)
0x18004034b  mov     ebx, eax
0x18004034d  test    eax, eax
0x18004034f  jz      loc_18004025B
0x180040355  mov     rdx, [rsp+150h+ProcessHandle]; void *
0x18004035a  call    ?GetIntegrityLevel@CCtfServerPort@@AEAAKPEAX@Z; CCtfServerPort::GetIntegrityLevel(void *)
0x18004035f  cmp     eax, ebx
0x180040361  jb      loc_18004025B
0x180040367  mov     edx, 0B0h; uBytes
0x18004036c  lea     ecx, [rdx-70h]; uFlags
0x18004036f  call    cs:__imp_LocalAlloc
0x180040375  xor     ebx, ebx
0x180040377  test    rax, rax
0x18004037a  jz      short loc_18004038B
0x18004037c  lea     rdx, [rbp+50h+var_A0]; struct MsgConnect *
0x180040380  mov     rcx, rax; this
0x180040383  call    ??0ImeServerInfo@CCtfServerPort@@QEAA@AEBUMsgConnect@@@Z; CCtfServerPort::ImeServerInfo::ImeServerInfo(MsgConnect const &)
0x180040388  mov     r14, rax
0x18004038b  mov     rdi, r14
0x18004038e  jmp     loc_18004023E
0x180040393  xor     edx, edx; Val
0x180040395  lea     rcx, [rbp+50h+var_A0]; void *
0x180040399  lea     r8d, [rdx+48h]; Size
0x18004039d  call    memset_0
0x1800403a2  mov     rdx, [rsi]
0x1800403a5  lea     rax, [rbp+50h+var_A0]
0x1800403a9  mov     byte ptr [rsp+150h+var_110], 1
0x1800403ae  lea     rcx, [rsp+150h+Handle]
0x1800403b3  mov     qword ptr [rsp+150h+var_118], rbx
0x1800403b8  xor     r9d, r9d
0x1800403bb  mov     [rsp+150h+var_120], r15
0x1800403c0  xor     r8d, r8d
0x1800403c3  mov     [rsp+150h+var_128], rdi
0x1800403c8  mov     [rsp+150h+ReturnLength], rax
0x1800403cd  mov     qword ptr [rbp+50h+var_90], 200h
0x1800403d5  mov     dword ptr [rbp+50h+var_A0], 80000h
0x1800403dc  mov     [rbp+50h+var_60], 10h
0x1800403e3  call    cs:__imp_NtAlpcAcceptConnectPort
0x1800403e9  mov     r12d, eax
0x1800403ec  jmp     loc_180040276
0x1800403f1  xor     ebx, ebx
0x1800403f3  mov     edi, ebx
0x1800403f5  jmp     loc_18004023E
0x1800403fa  mov     rcx, rdi; this
0x1800403fd  call    ?Release@ClientInfo@CCtfServerPort@@QEAAXXZ; CCtfServerPort::ClientInfo::Release(void)
0x180040402  mov     rdi, rbx
0x180040405  mov     [rsp+150h+var_E0], rbx
0x18004040a  jmp     loc_18004025B
0x18004040f  mov     rax, rdx
0x180040412  neg     rax
0x180040415  sbb     rcx, rcx
0x180040418  and     rcx, r14
0x18004041b  jmp     short loc_180040421
0x18004041d  mov     rcx, [rcx+58h]
0x180040421  cmp     [rcx+58h], rbx
0x180040425  jnz     short loc_18004041D
0x180040427  mov     [rcx+58h], r8
0x18004042b  mov     rax, [rsi+70h]
0x18004042f  mov     [rax+60h], rcx
0x180040433  jmp     loc_18004032B
0x180040438  lea     rdx, [rsp+150h+var_E0]; struct CCtfServerPort::ClientInfo **
0x18004043d  mov     rcx, rsi; this
0x180040440  call    ?RemoveClient@CCtfServerPort@@AEAA_NAEAPEAUClientInfo@1@@Z; CCtfServerPort::RemoveClient(CCtfServerPort::ClientInfo * &)
0x180040445  jmp     loc_180040288
```
