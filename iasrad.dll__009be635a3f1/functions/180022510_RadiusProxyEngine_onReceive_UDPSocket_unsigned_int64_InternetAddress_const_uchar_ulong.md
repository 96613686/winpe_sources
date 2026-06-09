# RadiusProxyEngine::onReceive(UDPSocket &,unsigned __int64,InternetAddress const &,uchar *,ulong)

- ea: `0x180022510`
- end: `0x18002302c`
- name: `?onReceive@RadiusProxyEngine@@EEAAXAEAVUDPSocket@@_KAEBUInternetAddress@@PEAEK@Z`
- size: `2844`
- prototype: `void __usercall(RadiusProxyEngine *__hidden this@<rcx>, struct UDPSocket *@<rdx>, unsigned __int64@<r8>, const struct InternetAddress *@<r9>, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `26`
- tags: ``

## callees

- `0x180002112`
- `0x1800094e4`
- `0x180014710`
- `0x18001d31c`
- `0x18001d9f8`
- `0x18001fcb0`
- `0x18001ff04`
- `0x180021228`
- `0x180021490`
- `0x180021564`
- `0x1800215a0`
- `0x180022510`
- `0x180023034`
- `0x180023ab8`
- `0x180024324`
- `0x1800249ec`
- `0x1800279a4`
- `0x180029cb4`
- `0x180029ee4`
- `0x18002d890`
- `0x18002d964`
- `0x18002df44`
- `0x18002e1f6`
- `0x18002e230`
- `0x18002e2f0`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800225d9`
- `KERNEL32!GetCurrentThreadId` at `0x1800225ff`
- `KERNEL32!GetCurrentThreadId` at `0x1800225d9`
- `KERNEL32!GetCurrentThreadId` at `0x1800225ff`

## string_xrefs

- `0x180022e79`: `Couldn't find the request in the pending requests. We assume this packet already timed out`
- `0x180022b26`: `Packet was valid but already timed out`

## pseudocode

```c
void __fastcall RadiusProxyEngine::onReceive(
        RadiusProxyEngine *this,
        struct UDPSocket *a2,
        int a3,
        const struct InternetAddress *a4,
        unsigned __int8 *a5,
        unsigned int a6)
{
  DWORD CurrentThreadId; // eax
  volatile signed __int32 *v10; // rdi
  DWORD v11; // eax
  void (__fastcall ***v12)(_QWORD, int *); // rcx
  RemoteServer *v13; // rcx
  int v14; // edx
  unsigned int v15; // edx
  unsigned __int8 *i; // rcx
  unsigned __int64 v17; // rbx
  struct HashTableEntry **v18; // rsi
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  _DWORD *v23; // rax
  unsigned __int8 *v24; // rdx
  struct HashTableEntry *v25; // r8
  __int64 v26; // rcx
  struct RadiusAttribute *Attribute; // r15
  _WORD *v28; // rax
  size_t v29; // rbx
  const void *v30; // rdx
  struct HashTableEntry *v31; // rax
  struct HashTableEntry *v32; // r15
  struct RemoteServer *v33; // rbx
  __int64 v34; // r10
  __int64 v35; // r10
  __int64 v36; // r10
  int v37; // eax
  int v38; // eax
  int v39; // eax
  unsigned __int8 v40; // di
  __int64 v41; // rdi
  __int64 *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // [rsp+0h] [rbp-40h] BYREF
  int v45; // [rsp+20h] [rbp-20h]
  __int64 v46; // [rsp+28h] [rbp-18h]
  struct HashTableEntry *v47; // [rsp+30h] [rbp-10h]
  struct HashTableEntry *v48; // [rsp+40h] [rbp+0h] BYREF
  struct HashTableEntry **v49; // [rsp+48h] [rbp+8h] BYREF
  int v50; // [rsp+50h] [rbp+10h] BYREF
  int v51; // [rsp+54h] [rbp+14h]
  struct RemoteServer *v52; // [rsp+58h] [rbp+18h]
  const struct InternetAddress *v53; // [rsp+60h] [rbp+20h]
  __int16 v54; // [rsp+68h] [rbp+28h]
  int v55; // [rsp+6Ah] [rbp+2Ah]
  __int16 v56; // [rsp+6Eh] [rbp+2Eh]
  unsigned __int8 *v57; // [rsp+70h] [rbp+30h]
  unsigned int v58; // [rsp+78h] [rbp+38h]
  int v59; // [rsp+7Ch] [rbp+3Ch]
  int v60; // [rsp+80h] [rbp+40h] BYREF
  int v61; // [rsp+84h] [rbp+44h]
  struct RemoteServer *v62; // [rsp+88h] [rbp+48h] BYREF
  __int64 *v63; // [rsp+90h] [rbp+50h]
  const struct InternetAddress *v64; // [rsp+98h] [rbp+58h]
  _BYTE *v65; // [rsp+A0h] [rbp+60h]

  v64 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Recieving a request from a remote server");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
  }
  v50 = a3;
  v51 = 0;
  v52 = 0;
  v53 = a4;
  v54 = *((_WORD *)a4 + 1);
  v55 = 0;
  v56 = 0;
  v57 = a5;
  v58 = a6;
  v59 = 0;
  CurrentThreadId = GetCurrentThreadId();
  Perimeter::Lock((RadiusProxyEngine *)((char *)this + 8328), CurrentThreadId);
  v10 = (volatile signed __int32 *)ObjectVector<RemoteServer>::search((char *)this + 8448, a4, findServerByAddress);
  v11 = GetCurrentThreadId();
  Perimeter::Unlock((RadiusProxyEngine *)((char *)this + 8328), v11);
  v62 = (struct RemoteServer *)v10;
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Invalid remote server address");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
    }
    v51 = 1;
    (***((void (__fastcall ****)(_QWORD, int *))this + 1))(*((_QWORD *)this + 1), &v50);
    return;
  }
  _InterlockedIncrement(v10 + 2);
  v52 = (struct RemoteServer *)v10;
  if ( !a6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Invalid packet type");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
    }
    v51 = 13;
LABEL_12:
    v12 = (void (__fastcall ***)(_QWORD, int *))*((_QWORD *)this + 1);
LABEL_13:
    (**v12)(v12, &v50);
LABEL_14:
    v13 = (RemoteServer *)v10;
LABEL_15:
    RemoteServer::Release(v13);
    return;
  }
  v14 = (unsigned __int16)a3 | (*a5 << 16);
  v12 = (void (__fastcall ***)(_QWORD, int *))*((_QWORD *)this + 1);
  switch ( v14 )
  {
    case 131072:
      v51 = 3;
      break;
    case 196608:
      v51 = 4;
      break;
    case 327681:
      v51 = 7;
      break;
    case 720896:
      v51 = 5;
      break;
    default:
      v51 = 13;
      goto LABEL_13;
  }
  (**v12)(v12, &v50);
  if ( a6 < 0x14 || (a5[3] | (a5[2] << 8)) != a6 )
    goto LABEL_127;
  v15 = 0;
  for ( i = a5 + 20; i < &a5[a6 - 1] && i[1] >= 2u; i += i[1] )
    ++v15;
  if ( i != &a5[a6] || v15 == -1 )
    goto LABEL_127;
  v17 = 16 * (v15 + 2LL);
  v18 = 0;
  if ( v17 > g_ulMaxStackAllocSize || v17 + g_ulAdditionalProbeSize + 8 < v17 || !(unsigned int)VerifyStackAvailable() )
    goto LABEL_137;
  v19 = v17 + 23;
  if ( v17 + 23 <= v17 + 8 )
    v19 = 0xFFFFFFFFFFFFFF0LL;
  v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
  v21 = alloca(v20);
  v22 = alloca(v20);
  v18 = &v48;
  if ( &v44 == (__int64 *)-64LL || (LODWORD(v48) = 1801679955, (v18 = (struct HashTableEntry **)&v49) == 0) )
  {
LABEL_137:
    if ( v17 + 8 >= v17 )
    {
      v23 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      v18 = (struct HashTableEntry **)v23;
      if ( v23 )
      {
        *v23 = 1885431112;
        v18 = (struct HashTableEntry **)(v23 + 2);
      }
    }
  }
  if ( !v18 )
  {
LABEL_127:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Invalid packet format");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
    }
    v51 = 8;
    goto LABEL_12;
  }
  v18[2] = (struct HashTableEntry *)(v18 + 4);
  v18[3] = (struct HashTableEntry *)&v18[v17 / 8];
  v49 = v18;
  *(_BYTE *)v18 = *a5;
  v65 = (char *)v18 + 1;
  *((_BYTE *)v18 + 1) = a5[1];
  *((_WORD *)v18 + 1) = _byteswap_ushort(*((_WORD *)a5 + 1));
  v18[1] = (struct HashTableEntry *)(a5 + 4);
  v24 = a5 + 20;
  v63 = (__int64 *)(v18 + 2);
  v25 = v18[2];
  while ( v24 < &a5[a6] )
  {
    *(_BYTE *)v25 = *v24;
    v26 = (unsigned __int8)(v24[1] - 2);
    *((_BYTE *)v25 + 1) = v26;
    *((_QWORD *)v25 + 1) = v24 + 2;
    v24 += v26 + 2;
    v25 = (struct HashTableEntry *)((char *)v25 + 16);
  }
  Attribute = FindAttribute((const struct RadiusPacket *)v18, 0x21u);
  v28 = (_WORD *)*((_QWORD *)this + 2);
  v29 = 16;
  if ( *v28 != 23 )
    v29 = 4;
  if ( !Attribute || *((unsigned __int8 *)Attribute + 1) != v29 + 4 )
    goto LABEL_122;
  v30 = v28 + 4;
  if ( *v28 != 23 )
    v30 = v28 + 2;
  if ( memcmp_0(*((const void **)Attribute + 1), v30, v29) )
  {
LABEL_122:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("The packet that we recieved was not expected - the attribute RADIUS_PROXY_STATE is invalid or doesn't "
                  "match our address");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
    }
    v51 = 14;
    (***((void (__fastcall ****)(_QWORD, int *))this + 1))(*((_QWORD *)this + 1), &v50);
    goto LABEL_119;
  }
  v61 = *(unsigned __int8 *)(*((_QWORD *)Attribute + 1) + v29 + 3)
      | ((*(unsigned __int8 *)(*((_QWORD *)Attribute + 1) + v29 + 2)
        | ((*(unsigned __int8 *)(*((_QWORD *)Attribute + 1) + v29 + 1)
          | (*(unsigned __int8 *)(*((_QWORD *)Attribute + 1) + v29) << 8)) << 8)) << 8);
  v18[3] = (struct HashTableEntry *)((char *)v18[3] - 16);
  memmove_0(Attribute, (char *)Attribute + 16, (v18[3] - Attribute) & 0xFFFFFFFFFFFFFFF0uLL);
  v60 = v61;
  v31 = HashTableBase::find((RadiusProxyEngine *)((char *)this + 8520), &v60);
  v32 = v31;
  if ( !v31 )
  {
    v48 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Couldn't find the request in the pending requests. We assume this packet already timed out");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
    }
    v51 = 15;
    (***((void (__fastcall ****)(_QWORD, int *))this + 1))(*((_QWORD *)this + 1), &v50);
    ObjectPointer<ServerBinding>::_release(&v48);
LABEL_119:
    SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v49);
    goto LABEL_14;
  }
  v48 = v31;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Packet matches a pending request. Now we'll validate it's authentic.");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
  }
  ObjectPointer<RemoteServer>::attach(&v62, *((_QWORD *)v32 + 7));
  v33 = v62;
  v52 = v62;
  v34 = *((_QWORD *)v32 + 7);
  if ( *((_BYTE *)v32 + 80) == 1 )
    v35 = v34 + 48;
  else
    v35 = v34 + 200;
  if ( (unsigned __int8)InternetAddress::operator==(v35 + 24, v64) && *((_BYTE *)v32 + 81) == *v65 )
  {
    v37 = AuthenticateAndDecrypt(
            (char *)v32 + 82,
            *(_QWORD *)v36,
            *(unsigned int *)(v36 + 8),
            a5,
            a6,
            v18,
            *((_DWORD *)v33 + 94));
    if ( v37 )
    {
      v38 = v37 - 1;
      if ( v38 )
      {
        v39 = v38 - 1;
        if ( v39 )
        {
          if ( v39 == 1 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            {
              WppDbgPrint("The packet's signature is missing: authResult = AUTH_MISSING_SIGNATURE_AUDIT");
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                55,
                &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids,
                "NPSRAD");
            }
            v51 = 21;
            (***((void (__fastcall ****)(_QWORD, int *))this + 1))(*((_QWORD *)this + 1), &v50);
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Packet is authentic.");
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              56,
              &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids,
              "NPSRAD");
          }
          v60 = v61;
          if ( HashTableBase::erase((RadiusProxyEngine *)((char *)this + 8520), &v60) )
          {
            v40 = *(_BYTE *)v18;
            *((_QWORD *)v32 + 8) = GetSystemTimeAsDWORDLONG() - *((_QWORD *)v32 + 8);
            Timer::cancelTimer((struct HashTableEntry *)((char *)v32 + 16));
            if ( RemoteServer::onReceive(*((RemoteServer **)v32 + 7), v40) )
            {
              v51 = 19;
              (***((void (__fastcall ****)(_QWORD, int *))this + 1))(*((_QWORD *)this + 1), &v50);
            }
            v59 = (*((_QWORD *)v32 + 8) + 50000LL) / 0x186A0uLL;
            v51 = 16;
            (***((void (__fastcall ****)(_QWORD, int *))this + 1))(*((_QWORD *)this + 1), &v50);
            RadiusProxyEngine::setServerAffinity(this, (const struct RadiusPacket *)v18, v33);
            RadiusProxyEngine::clearServerAvoidance(this, (const struct RadiusPacket *)v18, v33);
            v41 = _InterlockedExchange64((volatile __int64 *)(*((_QWORD *)v32 + 6) + 8LL), 0);
            if ( v41 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
              {
                WppDbgPrint("Successfully proccessed the response");
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  58,
                  &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids,
                  "NPSRAD");
              }
              v42 = (__int64 *)*((_QWORD *)this + 1);
              v43 = *v42;
              v47 = v18[3];
              v46 = *v63;
              LOBYTE(v45) = *(_BYTE *)v18;
              (*(void (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD, int, __int64, struct HashTableEntry *))(v43 + 8))(
                v42,
                0,
                v41,
                *((_QWORD *)v32 + 7),
                v45,
                v46,
                v47);
            }
            goto LABEL_107;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Packet was valid but already timed out");
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              57,
              &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids,
              "NPSRAD");
          }
          v51 = 15;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("The packet's signature is missing: authResult = AUTH_MISSING_SIGNATURE");
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              54,
              &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids,
              "NPSRAD");
          }
          v51 = 11;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("The packet's signature is invalid: authResult = AUTH_BAD_SIGNATURE");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
        }
        v51 = 10;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Packet is not authentic: authResult = AUTH_BAD_AUTHENTICATOR");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
      }
      v51 = 9;
    }
    (***((void (__fastcall ****)(_QWORD, int *))this + 1))(*((_QWORD *)this + 1), &v50);
LABEL_107:
    ObjectPointer<ServerBinding>::_release(&v48);
    SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v49);
LABEL_113:
    v13 = v33;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("The packet that we recieved was not expected - the source and/or identifier don't match");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
  }
  v51 = 14;
  (***((void (__fastcall ****)(_QWORD, int *))this + 1))(*((_QWORD *)this + 1), &v50);
  ObjectPointer<ServerBinding>::_release(&v48);
  SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v49);
  if ( v33 )
    goto LABEL_113;
}

```

## disassembly

```asm
0x180022510  push    rbp
0x180022512  push    rbx
0x180022513  push    rsi
0x180022514  push    rdi
0x180022515  push    r12
0x180022517  push    r13
0x180022519  push    r14
0x18002251b  push    r15
0x18002251d  sub     rsp, 0B8h
0x180022524  lea     rbp, [rsp+40h]
0x180022529  mov     rax, cs:__security_cookie
0x180022530  xor     rax, rbp
0x180022533  mov     [rbp+0B0h+var_48], rax
0x180022537  mov     rdi, r9
0x18002253a  mov     [rbp+0B0h+var_58], r9
0x18002253e  mov     rsi, r8
0x180022541  mov     r14, rcx
0x180022544  lea     rcx, WPP_GLOBAL_Control
0x18002254b  mov     rax, cs:WPP_GLOBAL_Control
0x180022552  cmp     rax, rcx
0x180022555  jz      short loc_180022595
0x180022557  cmp     byte ptr [rax+19h], 4
0x18002255b  jb      short loc_180022595
0x18002255d  test    dword ptr [rax+1Ch], 100h
0x180022564  jz      short loc_180022595
0x180022566  lea     rcx, aRecievingARequ; "Recieving a request from a remote serve"...
0x18002256d  call    WppDbgPrint
0x180022572  mov     edx, 2Ch ; ','
0x180022577  lea     r9, aNpsrad; "NPSRAD"
0x18002257e  lea     r8, WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids
0x180022585  mov     rcx, cs:WPP_GLOBAL_Control
0x18002258c  mov     rcx, [rcx+10h]
0x180022590  call    WPP_SF_s
0x180022595  mov     [rbp+0B0h+var_A0], esi
0x180022598  xor     r15d, r15d
0x18002259b  mov     [rbp+0B0h+var_9C], r15d
0x18002259f  mov     [rbp+0B0h+var_98], r15
0x1800225a3  mov     [rbp+0B0h+var_90], rdi
0x1800225a7  movzx   eax, word ptr [rdi+2]
0x1800225ab  mov     [rbp+0B0h+var_88], ax
0x1800225af  xor     eax, eax
0x1800225b1  mov     [rbp+0B0h+var_86], eax
0x1800225b4  mov     [rbp+0B0h+var_82], ax
0x1800225b8  mov     r12, [rbp+0B0h+arg_20]
0x1800225bf  mov     [rbp+0B0h+var_80], r12
0x1800225c3  mov     r13d, [rbp+0B0h+arg_28]
0x1800225ca  mov     [rbp+0B0h+var_78], r13d
0x1800225ce  mov     [rbp+0B0h+var_74], r15d
0x1800225d2  lea     rbx, [r14+2088h]
0x1800225d9  call    cs:__imp_GetCurrentThreadId
0x1800225df  mov     edx, eax; unsigned int
0x1800225e1  mov     rcx, rbx; this
0x1800225e4  call    ?Lock@Perimeter@@QEAAXK@Z; Perimeter::Lock(ulong)
0x1800225e9  lea     rcx, [rbx+78h]
0x1800225ed  lea     r8, ?findServerByAddress@@YAHPEBXPEBQEBVRemoteServer@@@Z; findServerByAddress(void const *,RemoteServer const * const *)
0x1800225f4  mov     rdx, rdi
0x1800225f7  call    ?search@?$ObjectVector@VRemoteServer@@@@QEBAPEAVRemoteServer@@PEBXP6AH0PEBQEBV2@@_E@Z; ObjectVector<RemoteServer>::search(void const *,int (*)(void const *,RemoteServer const * const *),...)
0x1800225fc  mov     rdi, rax
0x1800225ff  call    cs:__imp_GetCurrentThreadId
0x180022605  mov     edx, eax; unsigned int
0x180022607  mov     rcx, rbx; this
0x18002260a  call    ?Unlock@Perimeter@@QEAAXK@Z; Perimeter::Unlock(ulong)
0x18002260f  mov     [rbp+0B0h+var_68], rdi
0x180022613  test    rdi, rdi
0x180022616  jz      loc_180022FA3
0x18002261c  lock inc dword ptr [rdi+8]
0x180022620  mov     [rbp+0B0h+var_98], rdi
0x180022624  test    r13d, r13d
0x180022627  jnz     short loc_1800226A0
0x180022629  mov     rax, cs:WPP_GLOBAL_Control
0x180022630  lea     rcx, WPP_GLOBAL_Control
0x180022637  cmp     rax, rcx
0x18002263a  jz      short loc_180022679
0x18002263c  cmp     byte ptr [rax+19h], 2
0x180022640  jb      short loc_180022679
0x180022642  test    dword ptr [rax+1Ch], 100h
0x180022649  jz      short loc_180022679
0x18002264b  lea     rcx, aInvalidPacketT; "Invalid packet type"
0x180022652  call    WppDbgPrint
0x180022657  lea     edx, [r15+2Eh]
0x18002265b  lea     r9, aNpsrad; "NPSRAD"
0x180022662  lea     r8, WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids
0x180022669  mov     rcx, cs:WPP_GLOBAL_Control
0x180022670  mov     rcx, [rcx+10h]
0x180022674  call    WPP_SF_s
0x180022679  mov     [rbp+0B0h+var_9C], 0Dh
0x180022680  mov     rcx, [r14+8]
0x180022684  lea     rdx, [rbp+0B0h+var_A0]
0x180022688  mov     rax, [rcx]
0x18002268b  mov     rax, [rax]
0x18002268e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022693  mov     rcx, rdi; this
0x180022696  call    ?Release@RemoteServer@@QEAAXXZ; RemoteServer::Release(void)
0x18002269b  jmp     loc_18002300F
0x1800226a0  movzx   edx, byte ptr [r12]
0x1800226a5  shl     edx, 10h
0x1800226a8  movzx   eax, si
0x1800226ab  or      edx, eax
0x1800226ad  mov     rcx, [r14+8]
0x1800226b1  cmp     edx, 20000h
0x1800226b7  jz      short loc_1800226F9
0x1800226b9  cmp     edx, 30000h
0x1800226bf  jz      short loc_1800226F0
0x1800226c1  cmp     edx, 50001h
0x1800226c7  jz      short loc_1800226E7
0x1800226c9  cmp     edx, 0B0000h
0x1800226cf  lea     rdx, [rbp+0B0h+var_A0]
0x1800226d3  jz      short loc_1800226DE
0x1800226d5  mov     [rbp+0B0h+var_9C], 0Dh
0x1800226dc  jmp     short loc_180022688
0x1800226de  mov     [rbp+0B0h+var_9C], 5
0x1800226e5  jmp     short loc_180022704
0x1800226e7  mov     [rbp+0B0h+var_9C], 7
0x1800226ee  jmp     short loc_180022700
0x1800226f0  mov     [rbp+0B0h+var_9C], 4
0x1800226f7  jmp     short loc_180022700
0x1800226f9  mov     [rbp+0B0h+var_9C], 3
0x180022700  lea     rdx, [rbp+0B0h+var_A0]
0x180022704  mov     rax, [rcx]
0x180022707  mov     rax, [rax]
0x18002270a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002270f  cmp     r13d, 14h
0x180022713  jb      loc_180022F46
0x180022719  movzx   ecx, byte ptr [r12+2]
0x18002271f  shl     ecx, 8
0x180022722  movzx   eax, byte ptr [r12+3]
0x180022728  or      ecx, eax
0x18002272a  cmp     ecx, r13d
0x18002272d  jnz     loc_180022F46
0x180022733  mov     edx, r15d
0x180022736  lea     r9, [r12+r13]
0x18002273a  lea     rcx, [r12+14h]
0x18002273f  lea     r8, [r9-1]
0x180022743  jmp     short loc_180022754
0x180022745  cmp     byte ptr [rcx+1], 2
0x180022749  jb      short loc_180022759
0x18002274b  inc     edx
0x18002274d  movzx   eax, byte ptr [rcx+1]
0x180022751  add     rcx, rax
0x180022754  cmp     rcx, r8
0x180022757  jb      short loc_180022745
0x180022759  cmp     rcx, r9
0x18002275c  jnz     loc_180022F46
0x180022762  cmp     edx, 0FFFFFFFFh
0x180022765  jz      loc_180022F46
0x18002276b  mov     ebx, edx
0x18002276d  add     rbx, 2
0x180022771  shl     rbx, 4
0x180022775  mov     rsi, r15
0x180022778  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18002277f  ja      short loc_1800227D9
0x180022781  mov     rcx, cs:g_ulAdditionalProbeSize
0x180022788  add     rcx, 8
0x18002278c  add     rcx, rbx
0x18002278f  cmp     rcx, rbx
0x180022792  jb      short loc_1800227D9
0x180022794  call    VerifyStackAvailable
0x180022799  test    eax, eax
0x18002279b  jz      short loc_1800227D9
0x18002279d  lea     rax, [rbx+8]
0x1800227a1  lea     rcx, [rax+0Fh]
0x1800227a5  cmp     rcx, rax
0x1800227a8  ja      short loc_1800227B4
0x1800227aa  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800227b4  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800227b8  mov     rax, rcx
0x1800227bb  call    _alloca_probe
0x1800227c0  sub     rsp, rcx
0x1800227c3  lea     rsi, [rsp+0F0h+var_B0]
0x1800227c8  test    rsi, rsi
0x1800227cb  jz      short loc_1800227D9
0x1800227cd  mov     dword ptr [rsi], 6B637453h
0x1800227d3  add     rsi, 8
0x1800227d7  jnz     short loc_180022800
0x1800227d9  lea     rcx, [rbx+8]
0x1800227dd  cmp     rcx, rbx
0x1800227e0  jb      short loc_180022800
0x1800227e2  mov     rax, cs:g_pfnAllocate
0x1800227e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227ee  mov     rsi, rax
0x1800227f1  test    rax, rax
0x1800227f4  jz      short loc_180022800
0x1800227f6  mov     dword ptr [rax], 70616548h
0x1800227fc  add     rsi, 8
0x180022800  test    rsi, rsi
0x180022803  jz      loc_180022F46
0x180022809  lea     rcx, [rsi+20h]
0x18002280d  mov     [rsi+10h], rcx
0x180022811  lea     rcx, [rbx+rsi]
0x180022815  mov     [rsi+18h], rcx
0x180022819  mov     [rbp+0B0h+var_A8], rsi
0x18002281d  mov     al, [r12]
0x180022821  mov     [rsi], al
0x180022823  lea     rcx, [rsi+1]
0x180022827  mov     [rbp+0B0h+var_50], rcx
0x18002282b  mov     al, [r12+1]
0x180022830  mov     [rcx], al
0x180022832  movzx   ecx, byte ptr [r12+2]
0x180022838  shl     cx, 8
0x18002283c  movzx   eax, byte ptr [r12+3]
0x180022842  or      cx, ax
0x180022845  mov     [rsi+2], cx
0x180022849  lea     rax, [r12+4]
0x18002284e  mov     [rsi+8], rax
0x180022852  lea     rdx, [rax+10h]
0x180022856  lea     rax, [rsi+10h]
0x18002285a  mov     [rbp+0B0h+var_60], rax
0x18002285e  mov     r8, [rax]
0x180022861  lea     r9, [r12+r13]
0x180022865  jmp     short loc_180022888
0x180022867  mov     al, [rdx]
0x180022869  mov     [r8], al
0x18002286c  mov     al, [rdx+1]
0x18002286f  sub     al, 2
0x180022871  movzx   ecx, al
0x180022874  lea     rax, [rdx+2]
0x180022878  mov     [r8+1], cl
0x18002287c  mov     [r8+8], rax
0x180022880  lea     rdx, [rax+rcx]
0x180022884  lea     r8, [r8+10h]
0x180022888  cmp     rdx, r9
0x18002288b  jb      short loc_180022867
0x18002288d  mov     dl, 21h ; '!'; unsigned __int8
0x18002288f  mov     rcx, rsi; struct RadiusPacket *
0x180022892  call    ?FindAttribute@@YAPEAURadiusAttribute@@AEBURadiusPacket@@E@Z; FindAttribute(RadiusPacket const &,uchar)
0x180022897  mov     r15, rax
0x18002289a  mov     rax, [r14+10h]
0x18002289e  mov     ebx, 10h
0x1800228a3  cmp     word ptr [rax], 17h
0x1800228a7  lea     ecx, [rbx-0Ch]
0x1800228aa  cmovnz  ebx, ecx
0x1800228ad  test    r15, r15
0x1800228b0  jz      loc_180022ED9
0x1800228b6  movzx   edx, byte ptr [r15+1]
0x1800228bb  lea     rcx, [rbx+4]
0x1800228bf  cmp     rdx, rcx
0x1800228c2  jnz     loc_180022ED9
0x1800228c8  cmp     word ptr [rax], 17h
0x1800228cc  lea     rdx, [rax+8]
0x1800228d0  jz      short loc_1800228D6
0x1800228d2  lea     rdx, [rax+4]; Buf2
0x1800228d6  mov     r8, rbx; Size
0x1800228d9  mov     rcx, [r15+8]; Buf1
0x1800228dd  call    memcmp_0
0x1800228e2  test    eax, eax
0x1800228e4  jnz     loc_180022ED9
0x1800228ea  mov     rcx, [r15+8]
0x1800228ee  movzx   edx, byte ptr [rcx+rbx]
0x1800228f2  shl     edx, 8
0x1800228f5  movzx   eax, byte ptr [rcx+rbx+1]
0x1800228fa  or      edx, eax
0x1800228fc  shl     edx, 8
0x1800228ff  movzx   eax, byte ptr [rcx+rbx+2]
0x180022904  or      edx, eax
0x180022906  shl     edx, 8
0x180022909  movzx   eax, byte ptr [rcx+rbx+3]
0x18002290e  or      edx, eax
0x180022910  mov     [rbp+0B0h+var_6C], edx
0x180022913  add     qword ptr [rsi+18h], 0FFFFFFFFFFFFFFF0h
0x180022918  mov     r8, [rsi+18h]
0x18002291c  sub     r8, r15
0x18002291f  and     r8, 0FFFFFFFFFFFFFFF0h; Size
0x180022923  lea     rdx, [r15+10h]; Src
0x180022927  mov     rcx, r15; void *
0x18002292a  call    memmove_0
0x18002292f  mov     eax, [rbp+0B0h+var_6C]
0x180022932  mov     [rbp+0B0h+var_70], eax
0x180022935  lea     rcx, [r14+2148h]; this
0x18002293c  lea     rdx, [rbp+0B0h+var_70]; void *
0x180022940  call    ?find@HashTableBase@@QEAAPEAVHashTableEntry@@PEBX@Z; HashTableBase::find(void const *)
0x180022945  mov     r15, rax
0x180022948  test    rax, rax
0x18002294b  jz      loc_180022E4F
0x180022951  mov     [rbp+0B0h+var_B0], rax
0x180022955  mov     rax, cs:WPP_GLOBAL_Control
0x18002295c  lea     rcx, WPP_GLOBAL_Control
0x180022963  mov     edi, 100h
0x180022968  cmp     rax, rcx
0x18002296b  jz      short loc_1800229A7
0x18002296d  cmp     byte ptr [rax+19h], 4
0x180022971  jb      short loc_1800229A7
0x180022973  test    [rax+1Ch], edi
0x180022976  jz      short loc_1800229A7
0x180022978  lea     rcx, aPacketMatchesA; "Packet matches a pending request. Now w"...
0x18002297f  call    WppDbgPrint
0x180022984  mov     edx, 32h ; '2'
0x180022989  lea     r9, aNpsrad; "NPSRAD"
0x180022990  lea     r8, WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids
0x180022997  mov     rcx, cs:WPP_GLOBAL_Control
0x18002299e  mov     rcx, [rcx+10h]
0x1800229a2  call    WPP_SF_s
0x1800229a7  mov     rdx, [r15+38h]
0x1800229ab  lea     rcx, [rbp+0B0h+var_68]
0x1800229af  call    ?attach@?$ObjectPointer@VRemoteServer@@@@QEAAXPEAVRemoteServer@@@Z; ObjectPointer<RemoteServer>::attach(RemoteServer *)
0x1800229b4  mov     rbx, [rbp+0B0h+var_68]
0x1800229b8  mov     [rbp+0B0h+var_98], rbx
0x1800229bc  mov     r10, [r15+38h]
0x1800229c0  cmp     byte ptr [r15+50h], 1
0x1800229c5  jnz     short loc_1800229CD
0x1800229c7  add     r10, 30h ; '0'
  ... truncated ...
```
