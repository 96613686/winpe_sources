# RadiusProxyEngine::sendRequest(RadiusPacket &,bool,Request *)

- ea: `0x180023af8`
- end: `0x18002431b`
- name: `?sendRequest@RadiusProxyEngine@@AEAA?AW4Result@1@AEAURadiusPacket@@_NPEAVRequest@@@Z`
- size: `2083`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180021828`

## callees

- `0x180001fc8`
- `0x180002106`
- `0x1800094e4`
- `0x180014710`
- `0x180016244`
- `0x18001d31c`
- `0x18001ff04`
- `0x18001ff50`
- `0x180020128`
- `0x180020984`
- `0x1800214b4`
- `0x180021678`
- `0x180023464`
- `0x1800236a4`
- `0x180023af8`
- `0x1800249ec`
- `0x180024b68`
- `0x180026a44`
- `0x180026ec0`
- `0x1800279a4`
- `0x180027a6c`
- `0x180027e88`
- `0x18002c9d8`
- `0x18002da94`
- `0x18002df44`
- `0x18002e230`
- `0x18002e2f0`
- `0x180030010`

## import_xrefs

- `msvcrt!free` at `0x180023ed5`
- `msvcrt!free` at `0x18002408a`
- `msvcrt!free` at `0x180023ed5`
- `msvcrt!free` at `0x18002408a`
- `KERNEL32!EnterCriticalSection` at `0x180024120`
- `KERNEL32!EnterCriticalSection` at `0x180024120`
- `KERNEL32!LeaveCriticalSection` at `0x18002414e`
- `KERNEL32!LeaveCriticalSection` at `0x18002414e`
- `KERNEL32!GetLastError` at `0x180024002`
- `KERNEL32!GetLastError` at `0x180024219`
- `KERNEL32!GetLastError` at `0x180024002`
- `KERNEL32!GetLastError` at `0x180024219`
- `ADVAPI32!CryptGenRandom` at `0x180023dc7`
- `ADVAPI32!CryptGenRandom` at `0x180023dc7`

## string_xrefs

- `0x180023b67`: `Attempting to send radius request %d to server %S`
- `0x180023fc1`: `RadiusProxyEngine::sendRequest(), cannot reopen the socket for proxy`
- `0x18002427d`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RadiusProxyEngine::sendRequest(__int64 a1, __int64 a2, char a3, __int64 a4)
{
  int v7; // r9d
  int v8; // r12d
  size_t v9; // rsi
  struct InternetAddress **v10; // rbx
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  _DWORD *v15; // rax
  _WORD *v17; // rax
  __int64 v18; // rdx
  int v19; // edx
  _BYTE *v20; // rcx
  unsigned int v21; // esi
  unsigned __int16 BufferSizeRequired; // ax
  struct InternetAddress **v23; // rdi
  unsigned __int64 v24; // rbx
  __int64 v25; // rcx
  unsigned __int64 v26; // rcx
  void *v27; // rsp
  void *v28; // rsp
  _DWORD *v29; // rax
  __int64 v30; // r12
  __int64 v31; // rbx
  struct RemotePort *v32; // rbx
  struct RadiusAttribute *Attribute; // rax
  bool v34; // r8
  void **v35; // r12
  unsigned int v36; // ebx
  char v37; // cl
  __int64 v38; // rbx
  const struct RemotePort *v39; // rdi
  __int64 v40; // rbx
  RemotePort *v41; // rax
  unsigned int v42; // ebx
  bool v43; // bl
  unsigned int v44; // eax
  int v45; // edx
  int v46; // r8d
  int v47; // r9d
  int v48; // edx
  _WORD *v49; // rax
  _BYTE v50[32]; // [rsp+0h] [rbp-40h] BYREF
  int v51; // [rsp+20h] [rbp-20h]
  int v52; // [rsp+40h] [rbp+0h] BYREF
  struct InternetAddress *v53; // [rsp+48h] [rbp+8h] BYREF
  struct InternetAddress **v54; // [rsp+50h] [rbp+10h] BYREF
  struct RemotePort *v55; // [rsp+58h] [rbp+18h]
  struct InternetAddress **v56; // [rsp+60h] [rbp+20h] BYREF
  _BYTE v57[2]; // [rsp+68h] [rbp+28h] BYREF
  int v58; // [rsp+6Ah] [rbp+2Ah]
  __int16 v59; // [rsp+6Eh] [rbp+2Eh]
  struct InternetAddress **v60; // [rsp+70h] [rbp+30h]
  int v61; // [rsp+78h] [rbp+38h] BYREF
  int v62; // [rsp+7Ch] [rbp+3Ch]
  __int64 v63; // [rsp+80h] [rbp+40h]
  char *v64; // [rsp+88h] [rbp+48h]
  __int16 v65; // [rsp+90h] [rbp+50h]
  int v66; // [rsp+92h] [rbp+52h]
  __int16 v67; // [rsp+96h] [rbp+56h]
  struct InternetAddress **v68; // [rsp+98h] [rbp+58h]
  int v69; // [rsp+A0h] [rbp+60h]
  DWORD LastError; // [rsp+A4h] [rbp+64h]
  _BYTE v71[152]; // [rsp+A8h] [rbp+68h] BYREF
  BYTE pbBuffer[16]; // [rsp+140h] [rbp+100h] BYREF
  char Buffer[256]; // [rsp+150h] [rbp+110h] BYREF

  BYTE1(v52) = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Attempting to send radius request %d to server %S");
    WPP_SF_sdS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      (unsigned int)&WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids,
      v7,
      *(_DWORD *)(a4 + 76),
      *(_QWORD *)(*(_QWORD *)(a4 + 56) + 32LL));
  }
  *(_BYTE *)(a2 + 1) = *(_BYTE *)(a4 + 81);
  v8 = *(unsigned __int8 *)(*(_QWORD *)(a4 + 56) + 372LL);
  v9 = 16;
  if ( **(_WORD **)(a1 + 16) != 23 )
    v9 = 4;
  v10 = 0;
  if ( v9 + 4 > g_ulMaxStackAllocSize
    || v9 + 4 + g_ulAdditionalProbeSize + 8 < v9 + 4
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_14;
  }
  v11 = v9 + 27;
  if ( v9 + 27 <= v9 + 12 )
    v11 = 0xFFFFFFFFFFFFFF0LL;
  v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
  v13 = alloca(v12);
  v14 = alloca(v12);
  v10 = (struct InternetAddress **)&v52;
  if ( v50 == (_BYTE *)-64LL || (v52 = 1801679955, (v10 = &v53) == 0) )
  {
LABEL_14:
    if ( v9 + 12 >= v9 + 4 )
    {
      v15 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      if ( !v15 )
        return 1;
      *v15 = 1885431112;
      v10 = (struct InternetAddress **)(v15 + 2);
    }
    if ( !v10 )
      return 1;
  }
  LODWORD(v53) = v8;
  v56 = v10;
  v57[0] = 33;
  v57[1] = v9 + 4;
  v58 = 0;
  v59 = 0;
  v60 = v10;
  v17 = *(_WORD **)(a1 + 16);
  v18 = 4;
  if ( *v17 != 23 )
    v18 = 2;
  memcpy_0(v10, &v17[v18], v9);
  v19 = *(_DWORD *)(a4 + 76);
  *((_BYTE *)v10 + v9) = HIBYTE(v19);
  v20 = (char *)v10 + v9;
  v20[1] = BYTE2(v19);
  v21 = 1;
  v20[2] = BYTE1(v19);
  v20[3] = v19;
  BufferSizeRequired = GetBufferSizeRequired((const struct RadiusPacket *)a2, (const struct RadiusAttribute *)v57, v8);
  *(_WORD *)(a2 + 2) = BufferSizeRequired;
  if ( BufferSizeRequired )
  {
    v23 = 0;
    v24 = BufferSizeRequired;
    if ( BufferSizeRequired > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)BufferSizeRequired + g_ulAdditionalProbeSize + 8 < BufferSizeRequired
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_97;
    }
    v25 = v24 + 23;
    if ( v24 + 23 <= v24 + 8 )
      v25 = 0xFFFFFFFFFFFFFF0LL;
    v26 = v25 & 0xFFFFFFFFFFFFFFF0uLL;
    v27 = alloca(v26);
    v28 = alloca(v26);
    v23 = (struct InternetAddress **)&v52;
    if ( v50 == (_BYTE *)-64LL || (v52 = 1801679955, (v23 = &v53) == 0) )
    {
LABEL_97:
      if ( v24 + 8 >= v24 )
      {
        v29 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        v23 = (struct InternetAddress **)v29;
        if ( v29 )
        {
          *v29 = 1885431112;
          v23 = (struct InternetAddress **)(v29 + 2);
        }
      }
    }
    if ( v23 )
    {
      v54 = v23;
      v30 = *(_QWORD *)(a4 + 56);
      v31 = 48;
      if ( *(_BYTE *)(a4 + 80) != 1 )
        v31 = 200;
      if ( *(_BYTE *)a2 == 1 && !*(_QWORD *)(a2 + 8) )
      {
        if ( !CryptGenRandom(*(_QWORD *)(a1 + 8864), 0x10u, pbBuffer) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Failed to generate the request authenticator");
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              60,
              &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids,
              "NPSRAD");
          }
          SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v54);
          v21 = 7;
          goto LABEL_43;
        }
        *(_QWORD *)(a2 + 8) = pbBuffer;
      }
      v32 = (struct RemotePort *)(v30 + v31);
      v55 = v32;
      PackBuffer(
        *(PUCHAR *)v32,
        *((_DWORD *)v32 + 2),
        (struct RadiusPacket *)a2,
        (const struct RadiusAttribute *)v57,
        (int)v53,
        (unsigned __int8 *)v23,
        *(unsigned __int16 *)(a2 + 2));
      *(_OWORD *)(a4 + 82) = *(_OWORD *)((char *)v23 + 4);
      Attribute = FindAttribute((const struct RadiusPacket *)a2, 1u);
      if ( Attribute )
      {
        v35 = (void **)(a4 + 104);
        v53 = (struct InternetAddress *)*((_QWORD *)Attribute + 1);
        if ( *(struct InternetAddress **)(a4 + 104) != v53 )
        {
          v36 = *((unsigned __int8 *)Attribute + 1);
          free(*v35);
          *v35 = 0;
          RadiusOctets::alloc((RadiusOctets *)(a4 + 104), (const unsigned __int8 *)v53, v36);
          v32 = v55;
        }
      }
      if ( *(_BYTE *)(a4 + 80) == 1 )
      {
        v37 = 1;
        v61 = 0;
        v62 = 2;
      }
      else
      {
        v37 = 0;
        v61 = 1;
        v62 = 6;
      }
      LOBYTE(v52) = v37;
      v63 = *(_QWORD *)(a4 + 56);
      v53 = (struct RemotePort *)((char *)v32 + 24);
      v64 = (char *)v32 + 24;
      v65 = *((_WORD *)v32 + 13);
      v66 = 0;
      v67 = 0;
      v68 = v23;
      v69 = *(unsigned __int16 *)(a2 + 2);
      LastError = 0;
      v38 = a1 + 24;
      if ( !v37 )
        v38 = a1 + 4176;
      HashTableBase::insert((HashTableBase *)(a1 + 8520), (struct HashTableEntry *)a4, v34);
      if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v38 + 40), 1, 1)
        && !(unsigned int)UDPSocket::reOpen((UDPSocket *)v38, (struct PacketReceiver *)a1, (unsigned __int8)v52 ^ 1LL) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("RadiusProxyEngine::sendRequest(), cannot reopen the socket for proxy");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
        }
        HashTable<long,Request>::erase((HashTableBase *)(a1 + 8520));
        v62 = 17;
        LastError = GetLastError();
        (***(void (__fastcall ****)(_QWORD, int *))(a1 + 8))(*(_QWORD *)(a1 + 8), &v61);
        SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v54);
        v21 = 5;
        goto LABEL_43;
      }
      if ( (unsigned int)UDPSocket::send(
                           (UDPSocket *)v38,
                           v53,
                           (const unsigned __int8 *)v23,
                           *(unsigned __int16 *)(a2 + 2)) )
      {
        v39 = RemotePort::RemotePort((RemotePort *)v71, v55);
        *(_QWORD *)(a4 + 64) = GetSystemTimeAsDWORDLONG();
        v40 = *(_QWORD *)(a4 + 56);
        v41 = RemotePort::RemotePort((RemotePort *)Buffer, v39);
        RemoteServer::onSend(v40, v41);
        free(*(void **)v39);
        if ( BYTE1(v52) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Succeeded in sending the request");
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              62,
              &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids,
              "NPSRAD");
          }
          HashTable<long,Request>::erase((HashTableBase *)(a1 + 8520));
          v21 = 0;
          goto LABEL_93;
        }
        v42 = *(_DWORD *)(*(_QWORD *)(a4 + 56) + 360LL);
        Timer::cancelTimer((Timer *)(a4 + 16));
        *(_DWORD *)(a4 + 40) = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8592));
        v43 = TimerQueue::queueTimer((TimerQueue *)(a1 + 8584), (struct Timer *)(a4 + 16), v42);
        if ( v43 && !*(_BYTE *)(a1 + 8668) )
          TimerQueue::createWatcher((TimerQueue *)(a1 + 8584));
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8592));
        if ( v43 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Succeeded in sending the request");
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              63,
              &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids,
              "NPSRAD");
          }
          v21 = 0;
          goto LABEL_93;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("sending failed, couldn't set timer for the request");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
        }
      }
      else
      {
        v62 = 17;
        LastError = GetLastError();
        v44 = IASFormatSysErr(LastError, Buffer);
        if ( v44 >= 0x100uLL )
          _report_rangecheckfailure();
        Buffer[v44] = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
          WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), v45, v46, v47, v51, (__int64)Buffer);
        }
        if ( LastError - 10051 <= 0xE && (v48 = 24585, _bittest(&v48, LastError - 10051))
          || (v49 = *(_WORD **)(v38 + 24)) != 0 && *v49 && LastError == 10049 )
        {
          RemoteServer::onTimeout(*(RemoteServer **)(a4 + 56));
          v21 = 6;
        }
        else
        {
          v21 = 5;
        }
      }
      HashTable<long,Request>::erase((HashTableBase *)(a1 + 8520));
LABEL_93:
      (***(void (__fastcall ****)(_QWORD, int *))(a1 + 8))(*(_QWORD *)(a1 + 8), &v61);
      SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v54);
    }
  }
LABEL_43:
  SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v56);
  return v21;
}

```

## disassembly

```asm
0x180023af8  push    rbp
0x180023afa  push    rsi
0x180023afb  push    rdi
0x180023afc  push    r12
0x180023afe  push    r13
0x180023b00  push    r14
0x180023b02  push    r15
0x180023b04  sub     rsp, 260h
0x180023b0b  lea     rbp, [rsp+40h]
0x180023b10  mov     [rbp+250h+arg_10], rbx
0x180023b17  mov     rax, cs:__security_cookie
0x180023b1e  xor     rax, rbp
0x180023b21  mov     [rbp+250h+var_40], rax
0x180023b28  mov     r14, r9
0x180023b2b  mov     [rbp+250h+var_24F], r8b
0x180023b2f  mov     r15, rdx
0x180023b32  mov     r13, rcx
0x180023b35  lea     rcx, WPP_GLOBAL_Control
0x180023b3c  mov     ebx, 4
0x180023b41  mov     rax, cs:WPP_GLOBAL_Control
0x180023b48  cmp     rax, rcx
0x180023b4b  jz      short loc_180023BA2
0x180023b4d  cmp     [rax+19h], bl
0x180023b50  jb      short loc_180023BA2
0x180023b52  test    dword ptr [rax+1Ch], 100h
0x180023b59  jz      short loc_180023BA2
0x180023b5b  mov     r8, [r9+38h]
0x180023b5f  mov     r8, [r8+20h]
0x180023b63  mov     edx, [r9+4Ch]
0x180023b67  lea     rcx, aAttemptingToSe; "Attempting to send radius request %d to"...
0x180023b6e  call    WppDbgPrint
0x180023b73  mov     rax, [r14+38h]
0x180023b77  lea     edx, [rbx+37h]
0x180023b7a  mov     rax, [rax+20h]
0x180023b7e  mov     [rsp+290h+var_268], rax
0x180023b83  mov     eax, [r14+4Ch]
0x180023b87  mov     [rsp+290h+var_270], eax
0x180023b8b  lea     r8, WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids
0x180023b92  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b99  mov     rcx, [rcx+10h]
0x180023b9d  call    WPP_SF_sdS
0x180023ba2  mov     al, [r14+51h]
0x180023ba6  mov     [r15+1], al
0x180023baa  mov     rax, [r14+38h]
0x180023bae  movzx   r12d, byte ptr [rax+174h]
0x180023bb6  mov     rax, [r13+10h]
0x180023bba  mov     esi, 10h
0x180023bbf  cmp     word ptr [rax], 17h
0x180023bc3  cmovnz  rsi, rbx
0x180023bc7  lea     rdi, [rsi+4]
0x180023bcb  xor     edx, edx
0x180023bcd  mov     ebx, edx
0x180023bcf  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180023bd6  ja      short loc_180023C30
0x180023bd8  mov     rcx, cs:g_ulAdditionalProbeSize
0x180023bdf  add     rcx, 8
0x180023be3  add     rcx, rdi
0x180023be6  cmp     rcx, rdi
0x180023be9  jb      short loc_180023C30
0x180023beb  call    VerifyStackAvailable
0x180023bf0  test    eax, eax
0x180023bf2  jz      short loc_180023C30
0x180023bf4  lea     rax, [rdi+8]
0x180023bf8  lea     rcx, [rax+0Fh]
0x180023bfc  cmp     rcx, rax
0x180023bff  ja      short loc_180023C0B
0x180023c01  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180023c0b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180023c0f  mov     rax, rcx
0x180023c12  call    _alloca_probe
0x180023c17  sub     rsp, rcx
0x180023c1a  lea     rbx, [rsp+290h+var_250]
0x180023c1f  test    rbx, rbx
0x180023c22  jz      short loc_180023C30
0x180023c24  mov     dword ptr [rbx], 6B637453h
0x180023c2a  add     rbx, 8
0x180023c2e  jnz     short loc_180023C66
0x180023c30  lea     rcx, [rdi+8]
0x180023c34  cmp     rcx, rdi
0x180023c37  jb      short loc_180023C57
0x180023c39  mov     rax, cs:g_pfnAllocate
0x180023c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c45  mov     rbx, rax
0x180023c48  test    rax, rax
0x180023c4b  jz      short loc_180023C5C
0x180023c4d  mov     dword ptr [rax], 70616548h
0x180023c53  add     rbx, 8
0x180023c57  test    rbx, rbx
0x180023c5a  jnz     short loc_180023C66
0x180023c5c  mov     eax, 1
0x180023c61  jmp     loc_180023E3F
0x180023c66  mov     dword ptr [rbp+250h+var_248], r12d
0x180023c6a  mov     [rbp+250h+var_230], rbx
0x180023c6e  mov     [rbp+250h+var_228], 21h ; '!'
0x180023c72  mov     ecx, 4
0x180023c77  lea     eax, [rcx+rsi]
0x180023c7a  mov     [rbp+250h+var_227], al
0x180023c7d  xor     eax, eax
0x180023c7f  mov     [rbp+250h+var_226], eax
0x180023c82  mov     [rbp+250h+var_222], ax
0x180023c86  mov     [rbp+250h+var_220], rbx
0x180023c8a  mov     rax, [r13+10h]
0x180023c8e  lea     edx, [rcx+4]
0x180023c91  cmp     word ptr [rax], 17h
0x180023c95  cmovnz  edx, ecx
0x180023c98  add     rdx, rax; Src
0x180023c9b  mov     r8, rsi; Size
0x180023c9e  mov     rcx, rbx; void *
0x180023ca1  call    memcpy_0
0x180023ca6  mov     edx, [r14+4Ch]
0x180023caa  mov     eax, edx
0x180023cac  shr     eax, 18h
0x180023caf  mov     [rsi+rbx], al
0x180023cb2  lea     rcx, [rsi+rbx]
0x180023cb6  mov     eax, edx
0x180023cb8  shr     eax, 10h
0x180023cbb  mov     [rcx+1], al
0x180023cbe  mov     esi, 1
0x180023cc3  mov     eax, edx
0x180023cc5  shr     eax, 8
0x180023cc8  mov     [rcx+rsi+1], al
0x180023ccc  mov     [rcx+rsi+2], dl
0x180023cd0  mov     r8d, r12d; int
0x180023cd3  lea     rdx, [rbp+250h+var_228]; struct RadiusAttribute *
0x180023cd7  mov     rcx, r15; struct RadiusPacket *
0x180023cda  call    ?GetBufferSizeRequired@@YAKAEBURadiusPacket@@PEBURadiusAttribute@@H@Z; GetBufferSizeRequired(RadiusPacket const &,RadiusAttribute const *,int)
0x180023cdf  mov     [r15+2], ax
0x180023ce4  xor     r12d, r12d
0x180023ce7  test    ax, ax
0x180023cea  jz      loc_180023E34
0x180023cf0  mov     edi, r12d
0x180023cf3  movzx   ebx, ax
0x180023cf6  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180023cfd  ja      short loc_180023D57
0x180023cff  mov     rcx, cs:g_ulAdditionalProbeSize
0x180023d06  add     rcx, 8
0x180023d0a  add     rcx, rbx
0x180023d0d  cmp     rcx, rbx
0x180023d10  jb      short loc_180023D57
0x180023d12  call    VerifyStackAvailable
0x180023d17  test    eax, eax
0x180023d19  jz      short loc_180023D57
0x180023d1b  lea     rax, [rbx+8]
0x180023d1f  lea     rcx, [rax+0Fh]
0x180023d23  cmp     rcx, rax
0x180023d26  ja      short loc_180023D32
0x180023d28  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180023d32  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180023d36  mov     rax, rcx
0x180023d39  call    _alloca_probe
0x180023d3e  sub     rsp, rcx
0x180023d41  lea     rdi, [rsp+290h+var_250]
0x180023d46  test    rdi, rdi
0x180023d49  jz      short loc_180023D57
0x180023d4b  mov     dword ptr [rdi], 6B637453h
0x180023d51  add     rdi, 8
0x180023d55  jnz     short loc_180023D7E
0x180023d57  lea     rcx, [rbx+8]
0x180023d5b  cmp     rcx, rbx
0x180023d5e  jb      short loc_180023D7E
0x180023d60  mov     rax, cs:g_pfnAllocate
0x180023d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d6c  mov     rdi, rax
0x180023d6f  test    rax, rax
0x180023d72  jz      short loc_180023D7E
0x180023d74  mov     dword ptr [rax], 70616548h
0x180023d7a  add     rdi, 8
0x180023d7e  test    rdi, rdi
0x180023d81  jz      loc_180023E34
0x180023d87  mov     [rbp+250h+var_240], rdi
0x180023d8b  mov     r12, [r14+38h]
0x180023d8f  mov     ebx, 30h ; '0'
0x180023d94  mov     eax, 0C8h
0x180023d99  cmp     [r14+50h], sil
0x180023d9d  cmovnz  ebx, eax
0x180023da0  cmp     [r15], sil
0x180023da3  jnz     loc_180023E73
0x180023da9  cmp     qword ptr [r15+8], 0
0x180023dae  jnz     loc_180023E73
0x180023db4  lea     r8, [rbp+250h+pbBuffer]; pbBuffer
0x180023dbb  mov     edx, 10h; dwLen
0x180023dc0  mov     rcx, [r13+22A0h]; hProv
0x180023dc7  call    cs:__imp_CryptGenRandom
0x180023dcd  test    eax, eax
0x180023dcf  jnz     loc_180023E68
0x180023dd5  mov     rax, cs:WPP_GLOBAL_Control
0x180023ddc  lea     rcx, WPP_GLOBAL_Control
0x180023de3  cmp     rax, rcx
0x180023de6  jz      short loc_180023E26
0x180023de8  cmp     byte ptr [rax+19h], 2
0x180023dec  jb      short loc_180023E26
0x180023dee  test    dword ptr [rax+1Ch], 100h
0x180023df5  jz      short loc_180023E26
0x180023df7  lea     rcx, aFailedToGenera; "Failed to generate the request authenti"...
0x180023dfe  call    WppDbgPrint
0x180023e03  mov     edx, 3Ch ; '<'
0x180023e08  lea     r9, aNpsrad; "NPSRAD"
0x180023e0f  lea     r8, WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids
0x180023e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e1d  mov     rcx, [rcx+10h]
0x180023e21  call    WPP_SF_s
0x180023e26  lea     rcx, [rbp+250h+var_240]; this
0x180023e2a  call    ??1SafeAllocaScopeGuard@@QEAA@XZ; SafeAllocaScopeGuard::~SafeAllocaScopeGuard(void)
0x180023e2f  mov     esi, 7
0x180023e34  lea     rcx, [rbp+250h+var_230]; this
0x180023e38  call    ??1SafeAllocaScopeGuard@@QEAA@XZ; SafeAllocaScopeGuard::~SafeAllocaScopeGuard(void)
0x180023e3d  mov     eax, esi
0x180023e3f  mov     rcx, [rbp+250h+var_40]
0x180023e46  xor     rcx, rbp; StackCookie
0x180023e49  call    __security_check_cookie
0x180023e4e  mov     rbx, [rbp+250h+arg_10]
0x180023e55  lea     rsp, [rbp+220h]
0x180023e5c  pop     r15
0x180023e5e  pop     r14
0x180023e60  pop     r13
0x180023e62  pop     r12
0x180023e64  pop     rdi
0x180023e65  pop     rsi
0x180023e66  pop     rbp
0x180023e67  retn
0x180023e68  lea     rax, [rbp+250h+pbBuffer]
0x180023e6f  mov     [r15+8], rax
0x180023e73  add     rbx, r12
0x180023e76  mov     [rbp+250h+var_238], rbx
0x180023e7a  movzx   eax, word ptr [r15+2]
0x180023e7f  mov     [rsp+290h+var_260], eax; unsigned int
0x180023e83  mov     [rsp+290h+var_268], rdi; unsigned __int8 *
0x180023e88  mov     eax, dword ptr [rbp+250h+var_248]
0x180023e8b  mov     [rsp+290h+var_270], eax; int
0x180023e8f  lea     r9, [rbp+250h+var_228]; struct RadiusAttribute *
0x180023e93  mov     r8, r15; struct RadiusPacket *
0x180023e96  mov     edx, [rbx+8]; unsigned int
0x180023e99  mov     rcx, [rbx]; pbSecret
0x180023e9c  call    ?PackBuffer@@YAXPEBEKAEAURadiusPacket@@PEBURadiusAttribute@@HPEAEK@Z; PackBuffer(uchar const *,ulong,RadiusPacket &,RadiusAttribute const *,int,uchar *,ulong)
0x180023ea1  movups  xmm0, xmmword ptr [rdi+4]
0x180023ea5  movdqu  xmmword ptr [r14+52h], xmm0
0x180023eab  mov     dl, sil; unsigned __int8
0x180023eae  mov     rcx, r15; struct RadiusPacket *
0x180023eb1  call    ?FindAttribute@@YAPEAURadiusAttribute@@AEBURadiusPacket@@E@Z; FindAttribute(RadiusPacket const &,uchar)
0x180023eb6  test    rax, rax
0x180023eb9  jz      short loc_180023EF6
0x180023ebb  lea     r12, [r14+68h]
0x180023ebf  mov     rcx, [rax+8]
0x180023ec3  mov     [rbp+250h+var_248], rcx
0x180023ec7  cmp     [r12], rcx
0x180023ecb  jz      short loc_180023EF6
0x180023ecd  movzx   ebx, byte ptr [rax+1]
0x180023ed1  mov     rcx, [r12]; Block
0x180023ed5  call    cs:__imp_free
0x180023edb  mov     qword ptr [r12], 0
0x180023ee3  mov     r8d, ebx; unsigned int
0x180023ee6  mov     rdx, [rbp+250h+var_248]; unsigned __int8 *
0x180023eea  mov     rcx, r12; this
0x180023eed  call    ?alloc@RadiusOctets@@AEAAXPEBEK@Z; RadiusOctets::alloc(uchar const *,ulong)
0x180023ef2  mov     rbx, [rbp+250h+var_238]
0x180023ef6  cmp     [r14+50h], sil
0x180023efa  jnz     short loc_180023F0F
0x180023efc  mov     cl, sil
0x180023eff  mov     [rbp+250h+var_218], 0
0x180023f06  mov     [rbp+250h+var_214], 2
0x180023f0d  jmp     short loc_180023F1B
0x180023f0f  xor     cl, cl
0x180023f11  mov     [rbp+250h+var_218], esi
0x180023f14  mov     [rbp+250h+var_214], 6
0x180023f1b  mov     [rbp+250h+var_250], cl
0x180023f1e  mov     rax, [r14+38h]
0x180023f22  mov     [rbp+250h+var_210], rax
0x180023f26  lea     rax, [rbx+18h]
0x180023f2a  mov     [rbp+250h+var_248], rax
0x180023f2e  mov     [rbp+250h+var_208], rax
0x180023f32  movzx   eax, word ptr [rbx+1Ah]
0x180023f36  mov     [rbp+250h+var_200], ax
0x180023f3a  xor     eax, eax
0x180023f3c  mov     [rbp+250h+var_1FE], eax
0x180023f3f  mov     [rbp+250h+var_1FA], ax
0x180023f43  mov     [rbp+250h+var_1F8], rdi
0x180023f47  movzx   eax, word ptr [r15+2]
0x180023f4c  mov     [rbp+250h+var_1F0], eax
0x180023f4f  xor     eax, eax
0x180023f51  mov     [rbp+250h+var_1EC], eax
0x180023f54  test    cl, cl
0x180023f56  lea     rbx, [r13+18h]
0x180023f5a  jnz     short loc_180023F63
0x180023f5c  lea     rbx, [r13+1050h]
0x180023f63  lea     r12, [r13+2148h]
0x180023f6a  mov     rdx, r14; struct HashTableEntry *
0x180023f6d  mov     rcx, r12; this
0x180023f70  call    ?insert@HashTableBase@@QEAA_NAEAVHashTableEntry@@_N@Z; HashTableBase::insert(HashTableEntry &,bool)
0x180023f75  mov     eax, esi
0x180023f77  lock cmpxchg [rbx+28h], esi
0x180023f7c  test    eax, eax
0x180023f7e  jnz     loc_180024031
0x180023f84  movzx   r8d, [rbp+250h+var_250]
0x180023f89  xor     r8, rsi; unsigned __int64
0x180023f8c  mov     rdx, r13; struct PacketReceiver *
0x180023f8f  mov     rcx, rbx; this
0x180023f92  call    ?reOpen@UDPSocket@@QEAAHPEAVPacketReceiver@@_K@Z; UDPSocket::reOpen(PacketReceiver *,unsigned __int64)
0x180023f97  test    eax, eax
0x180023f99  jnz     loc_180024031
0x180023f9f  mov     rax, cs:WPP_GLOBAL_Control
  ... truncated ...
```
