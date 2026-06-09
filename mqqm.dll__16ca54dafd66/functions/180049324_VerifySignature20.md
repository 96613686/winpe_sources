# VerifySignature20

- ea: `0x180049324`
- end: `0x1800498e0`
- name: `VerifySignature20`
- size: `1468`
- prototype: `__int64 __fastcall(CQmPacket *this, HCRYPTPROV hProv)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800499e4`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x18002b19c`
- `0x18002c61c`
- `0x18002c6c8`
- `0x18003dcdc`
- `0x18003de94`
- `0x18003e314`
- `0x18003e3d8`
- `0x18003e684`
- `0x180047908`
- `0x180048958`
- `0x180049324`
- `0x180049c5c`
- `0x180049d0c`
- `0x180049df0`
- `0x18009bd1c`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x1800495b2`
- `msvcrt!free` at `0x180049714`
- `msvcrt!free` at `0x180049720`
- `msvcrt!free` at `0x1800497b8`
- `msvcrt!free` at `0x1800497c4`
- `msvcrt!free` at `0x18004983a`
- `msvcrt!free` at `0x180049846`
- `msvcrt!free` at `0x18004986a`
- `msvcrt!free` at `0x180049876`
- `msvcrt!free` at `0x1800495b2`
- `msvcrt!free` at `0x180049714`
- `msvcrt!free` at `0x180049720`
- `msvcrt!free` at `0x1800497b8`
- `msvcrt!free` at `0x1800497c4`
- `msvcrt!free` at `0x18004983a`
- `msvcrt!free` at `0x180049846`
- `msvcrt!free` at `0x18004986a`
- `msvcrt!free` at `0x180049876`
- `ADVAPI32!CryptCreateHash` at `0x18004946b`
- `ADVAPI32!CryptCreateHash` at `0x18004946b`
- `ADVAPI32!CryptVerifySignatureW` at `0x180049754`
- `ADVAPI32!CryptVerifySignatureW` at `0x180049754`
- `KERNEL32!GetLastError` at `0x180049475`
- `KERNEL32!GetLastError` at `0x18004975e`
- `KERNEL32!GetLastError` at `0x180049475`
- `KERNEL32!GetLastError` at `0x18004975e`
- `mqsec!MQSigHashMessageProperties` at `0x1800496f0`
- `mqsec!MQSigHashMessageProperties` at `0x1800496f0`
- `mqsec!HashMessageProperties` at `0x180049518`
- `mqsec!HashMessageProperties` at `0x180049518`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall VerifySignature20(CUserHeader **this, HCRYPTPROV hProv, HCRYPTKEY a3, char a4)
{
  const unsigned __int8 *PacketBody; // r12
  CUserHeader *v8; // rdi
  unsigned __int8 *v9; // r9
  int v10; // ebx
  unsigned __int8 *v11; // r9
  int v12; // eax
  const struct QUEUE_FORMAT *v13; // rbx
  const struct QUEUE_FORMAT *v14; // rdi
  CSecurityHeader *v15; // rcx
  const unsigned __int8 *Section; // rax
  __int64 SubSection; // r14
  DWORD v18; // eax
  DWORD v19; // edi
  unsigned int v20; // ebx
  int v21; // eax
  int DestinationFormatName; // eax
  CUserHeader *v23; // rdx
  CUserHeader *v24; // rcx
  _DWORD *v25; // rdi
  unsigned __int8 *v26; // r9
  GUID *v27; // r12
  CUserHeader *v28; // r15
  unsigned int v29; // ecx
  int v30; // ebx
  unsigned __int8 *v31; // r9
  int v32; // ebx
  unsigned __int8 *v33; // r9
  GUID *v34; // rcx
  int v35; // eax
  DWORD LastError; // eax
  PVOID *v37; // rcx
  CUserHeader *v38; // rax
  unsigned int v40; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  HCRYPTHASH hHash; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v43; // [rsp+68h] [rbp-98h] BYREF
  HCRYPTKEY hPubKey; // [rsp+70h] [rbp-90h]
  _DWORD *v45; // [rsp+78h] [rbp-88h]
  _OWORD v46[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v47[2]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v48[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v49; // [rsp+E0h] [rbp-20h] BYREF
  int v50; // [rsp+E8h] [rbp-18h]
  GUID v51; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t v52[256]; // [rsp+100h] [rbp+0h] BYREF

  hPubKey = a3;
  v40 = 0;
  PacketBody = CQmPacket::GetPacketBody((CQmPacket *)this, &v40);
  memset(v46, 0, sizeof(v46));
  v8 = this[6];
  v10 = CUserHeader::QueueSize(
          *((_DWORD *)v8 + 11) & 0x1000000,
          (*((_DWORD *)v8 + 11) >> 10) & 7,
          (const unsigned __int8 *)v8 + 48,
          v9);
  v12 = CUserHeader::QueueSize(
          0,
          (unsigned __int8)HIBYTE(*((_WORD *)v8 + 22)) >> 5,
          (const unsigned __int8 *)v8 + v10 + 48,
          v11);
  v13 = (const struct QUEUE_FORMAT *)((unsigned __int64)v46
                                    & -(__int64)((unsigned int)CUserHeader::GetQueue(
                                                                 v8,
                                                                 (const unsigned __int8 *)v8 + v10 + v12 + 48,
                                                                 0,
                                                                 *((_WORD *)v8 + 23) & 7,
                                                                 (struct QUEUE_FORMAT *)v46) != 0));
  memset(v47, 0, sizeof(v47));
  v14 = (const struct QUEUE_FORMAT *)((unsigned __int64)v47
                                    & -(__int64)((unsigned int)CUserHeader::GetAdminQueue(
                                                                 this[6],
                                                                 (struct QUEUE_FORMAT *)v47) != 0));
  v15 = this[8];
  if ( v15 )
  {
    Section = CSecurityHeader::GetSectionExPtr(v15);
    if ( Section )
    {
      SubSection = pGetSubSectionEx(1, Section, 0);
      if ( SubSection )
      {
        hHash = 0;
        if ( CryptCreateHash(hProv, *((_DWORD *)this[9] + 11), 0, 0, &hHash) )
        {
          v21 = HashMessageProperties(
                  hHash,
                  (const unsigned __int8 *)this[9] + 4,
                  0x14u,
                  *((_DWORD *)this[9] + 7),
                  PacketBody,
                  v40,
                  (const wchar_t *)this[9] + 28,
                  2 * *((unsigned __int8 *)this[9] + 1),
                  v13,
                  v14);
          v20 = v21;
          if ( v21 >= 0 )
          {
            memset(v48, 0, sizeof(v48));
            CQmPacket::GetDestinationQueue((CQmPacket *)this, (struct QUEUE_FORMAT *)v48, 0);
            v40 = 256;
            v43 = 0;
            Block = 0;
            DestinationFormatName = _GetDestinationFormatName(
                                      (struct QUEUE_FORMAT *)v48,
                                      v52,
                                      &v40,
                                      (wchar_t **)&Block,
                                      &v43);
            v20 = DestinationFormatName;
            if ( DestinationFormatName >= 0 )
            {
              v49 = 0;
              v50 = 0;
              v23 = this[6];
              LOBYTE(v49) = (*((_DWORD *)v23 + 11) >> 5) & 3;
              BYTE1(v49) = *((_BYTE *)this[5] + 2) & 7;
              BYTE2(v49) = BYTE1(*((_DWORD *)v23 + 11)) & 3;
              v24 = this[9];
              BYTE3(v49) = *(_BYTE *)v24;
              WORD2(v49) = *((_WORD *)v24 + 1);
              v50 = *((_DWORD *)v24 + 6);
              v25 = MmAllocate(0x48u);
              v45 = v25;
              *v25 = 3;
              v25[2] = v40;
              *((_QWORD *)v25 + 2) = v43;
              v25[6] = 16;
              *((_QWORD *)v25 + 4) = this[6];
              v25[10] = 12;
              *((_QWORD *)v25 + 6) = &v49;
              v51 = GUID_NULL;
              if ( (*(_BYTE *)(SubSection + 6) & 8) != 0 )
              {
                v27 = &v51;
                v28 = this[6];
                v29 = *((_DWORD *)v28 + 11);
                if ( (v29 & 0x400000) != 0 )
                {
                  v30 = CUserHeader::QueueSize(v29 & 0x1000000, (v29 >> 10) & 7, (const unsigned __int8 *)v28 + 48, v26);
                  v32 = CUserHeader::QueueSize(
                          0,
                          (unsigned __int8)HIBYTE(*((_WORD *)v28 + 22)) >> 5,
                          (const unsigned __int8 *)v28 + v30 + 48,
                          v31)
                      + v30;
                  v34 = (GUID *)((char *)v28
                               + (int)(v32
                                     + CUserHeader::QueueSize(
                                         0,
                                         *((_WORD *)v28 + 23) & 7,
                                         (const unsigned __int8 *)v28 + v32 + 48,
                                         v33))
                               + 48);
                  if ( v34 )
                    v27 = v34;
                }
                v25[14] = 16;
                *((_QWORD *)v25 + 8) = v27;
                *v25 = 4;
              }
              v35 = MQSigHashMessageProperties(hHash, (struct _MsgHashData *)v25);
              v20 = v35;
              if ( v35 >= 0 )
              {
                if ( CryptVerifySignatureW(
                       hHash,
                       (const BYTE *)(SubSection + 8),
                       *(unsigned __int16 *)(SubSection + 4) - 8,
                       hPubKey,
                       0,
                       0) )
                {
                  v37 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 38, WPP_c687450366573ca356992ecf9dac13b8_Traceguids);
                    v37 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( a4 )
                  {
                    v38 = this[8];
                    if ( v38 )
                      *(_WORD *)v38 |= 0x10u;
                    CQmPacket::SetLevelOfAuthentication((CQmPacket *)this, 3u);
                    free(v25);
                    free(Block);
                  }
                  else
                  {
                    if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 268) & 4) != 0 )
                      WPP_SF_(v37[32], 39, WPP_c687450366573ca356992ecf9dac13b8_Traceguids);
                    free(v25);
                    free(Block);
                  }
                  v20 = 0;
                }
                else
                {
                  LastError = GetLastError();
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 32),
                      37,
                      WPP_c687450366573ca356992ecf9dac13b8_Traceguids,
                      LastError);
                  v20 = -1072824190;
                  LogMsgHR(-1072824190, (wchar_t *)L"qmsecutl", 0x477u);
                  free(v25);
                  free(Block);
                }
              }
              else
              {
                LogMsgHR(v35, (wchar_t *)L"qmsecutl", 0x406u);
                free(v25);
                free(Block);
              }
            }
            else
            {
              LogMsgNTStatus(DestinationFormatName, (wchar_t *)L"qmsecutl", 0x398u);
              free(Block);
            }
          }
          else
          {
            LogMsgHR(v21, (wchar_t *)L"qmsecutl", 0x3F2u);
          }
        }
        else
        {
          v18 = GetLastError();
          v19 = v18;
          if ( v18 )
            LogMsgNTStatus(v18, (wchar_t *)L"qmsecutl", 0x384u);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 36, WPP_c687450366573ca356992ecf9dac13b8_Traceguids, v19);
          v20 = -1072824191;
        }
        CHashHandle::~CHashHandle((CHashHandle *)&hHash);
        return v20;
      }
    }
  }
  if ( (unsigned int)AcceptOnlyEnhAuthn() )
  {
    v20 = -1072824190;
    LogMsgHR(-1072824190, (wchar_t *)L"qmsecutl", 0x394u);
    return v20;
  }
  return 1074660333;
}

```

## disassembly

```asm
0x180049324  mov     [rsp-8+arg_18], rbx
0x180049329  push    rbp
0x18004932a  push    rsi
0x18004932b  push    rdi
0x18004932c  push    r12
0x18004932e  push    r13
0x180049330  push    r14
0x180049332  push    r15
0x180049334  lea     rbp, [rsp-210h]
0x18004933c  sub     rsp, 310h
0x180049343  mov     rax, cs:__security_cookie
0x18004934a  xor     rax, rsp
0x18004934d  mov     [rbp+240h+var_40], rax
0x180049354  mov     r13b, r9b
0x180049357  mov     [rsp+340h+hPubKey], r8
0x18004935c  mov     r15, rdx
0x18004935f  mov     rsi, rcx
0x180049362  mov     [rsp+340h+var_2F0], 0
0x18004936a  lea     rdx, [rsp+340h+var_2F0]; unsigned int *
0x18004936f  call    ?GetPacketBody@CQmPacket@@QEBAPEBEPEAK@Z; CQmPacket::GetPacketBody(ulong *)
0x180049374  mov     r12, rax
0x180049377  xorps   xmm0, xmm0
0x18004937a  movups  [rbp+240h+var_2C0], xmm0
0x18004937e  movups  [rbp+240h+var_2B0], xmm0
0x180049382  mov     rdi, [rsi+30h]
0x180049386  mov     ecx, [rdi+2Ch]
0x180049389  lea     r8, [rdi+30h]; unsigned __int8 *
0x18004938d  mov     edx, ecx
0x18004938f  shr     edx, 0Ah
0x180049392  and     edx, 7; unsigned int
0x180049395  shr     ecx, 18h
0x180049398  and     cl, 1; bool
0x18004939b  call    ?QueueSize@CUserHeader@@CAH_NKPEBEPEAE@Z; CUserHeader::QueueSize(bool,ulong,uchar const *,uchar *)
0x1800493a0  movsxd  rbx, eax
0x1800493a3  lea     r8, [rdi+30h]
0x1800493a7  add     r8, rbx; unsigned __int8 *
0x1800493aa  mov     edx, [rdi+2Ch]
0x1800493ad  shr     edx, 0Dh
0x1800493b0  and     edx, 7; unsigned int
0x1800493b3  xor     ecx, ecx; bool
0x1800493b5  call    ?QueueSize@CUserHeader@@CAH_NKPEBEPEAE@Z; CUserHeader::QueueSize(bool,ulong,uchar const *,uchar *)
0x1800493ba  add     eax, ebx
0x1800493bc  movzx   r9d, word ptr [rdi+2Eh]
0x1800493c1  and     r9d, 7; unsigned int
0x1800493c5  cdqe
0x1800493c7  lea     rdx, [rdi+30h]
0x1800493cb  add     rdx, rax; unsigned __int8 *
0x1800493ce  lea     rax, [rbp+240h+var_2C0]
0x1800493d2  mov     [rsp+340h+phHash], rax; struct QUEUE_FORMAT *
0x1800493d7  xor     r8d, r8d; bool
0x1800493da  mov     rcx, rdi; this
0x1800493dd  call    ?GetQueue@CUserHeader@@AEBAHPEBE_NKPEAUQUEUE_FORMAT@@@Z; CUserHeader::GetQueue(uchar const *,bool,ulong,QUEUE_FORMAT *)
0x1800493e2  neg     eax
0x1800493e4  sbb     rbx, rbx
0x1800493e7  lea     rax, [rbp+240h+var_2C0]
0x1800493eb  and     rbx, rax
0x1800493ee  xorps   xmm0, xmm0
0x1800493f1  movups  [rbp+240h+var_2A0], xmm0
0x1800493f5  movups  [rbp+240h+var_290], xmm0
0x1800493f9  lea     rdx, [rbp+240h+var_2A0]; struct QUEUE_FORMAT *
0x1800493fd  mov     rcx, [rsi+30h]; this
0x180049401  call    ?GetAdminQueue@CUserHeader@@QEBAHPEAUQUEUE_FORMAT@@@Z; CUserHeader::GetAdminQueue(QUEUE_FORMAT *)
0x180049406  neg     eax
0x180049408  sbb     rdi, rdi
0x18004940b  lea     rax, [rbp+240h+var_2A0]
0x18004940f  and     rdi, rax
0x180049412  mov     rcx, [rsi+40h]; this
0x180049416  test    rcx, rcx
0x180049419  jz      loc_18004988B
0x18004941f  call    ?GetSectionExPtr@CSecurityHeader@@AEBAPEBEXZ; CSecurityHeader::GetSectionExPtr(void)
0x180049424  test    rax, rax
0x180049427  jz      loc_18004988B
0x18004942d  xor     r8d, r8d
0x180049430  mov     rdx, rax
0x180049433  lea     ecx, [r8+1]
0x180049437  call    ?pGetSubSectionEx@@YAPEAU_SecuritySubSectionEx@@W4enumSecInfoType@@PEBE1@Z; pGetSubSectionEx(enumSecInfoType,uchar const *,uchar const *)
0x18004943c  mov     r14, rax
0x18004943f  test    rax, rax
0x180049442  jz      loc_18004988B
0x180049448  mov     [rsp+340h+hHash], 0
0x180049451  mov     rdx, [rsi+48h]
0x180049455  lea     rax, [rsp+340h+hHash]
0x18004945a  mov     [rsp+340h+phHash], rax; phHash
0x18004945f  xor     r9d, r9d; dwFlags
0x180049462  xor     r8d, r8d; hKey
0x180049465  mov     edx, [rdx+2Ch]; Algid
0x180049468  mov     rcx, r15; hProv
0x18004946b  call    cs:__imp_CryptCreateHash
0x180049471  test    eax, eax
0x180049473  jnz     short loc_1800494D6
0x180049475  call    cs:__imp_GetLastError
0x18004947b  mov     edi, eax
0x18004947d  test    eax, eax
0x18004947f  jz      short loc_180049495
0x180049481  mov     r8d, 384h; unsigned __int16
0x180049487  lea     rdx, aQmsecutl; "qmsecutl"
0x18004948e  mov     ecx, eax; int
0x180049490  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180049495  lea     rbx, WPP_GLOBAL_Control
0x18004949c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800494a3  cmp     rcx, rbx
0x1800494a6  jz      short loc_1800494CC
0x1800494a8  test    byte ptr [rcx+10Ch], 1
0x1800494af  jz      short loc_1800494CC
0x1800494b1  mov     edx, 24h ; '$'
0x1800494b6  mov     r9d, edi
0x1800494b9  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x1800494c0  mov     rcx, [rcx+100h]
0x1800494c7  call    WPP_SF_d
0x1800494cc  mov     ebx, 0C00E0081h
0x1800494d1  jmp     loc_18004987F
0x1800494d6  mov     r9, [rsi+48h]
0x1800494da  movzx   ecx, byte ptr [r9+1]
0x1800494df  add     ecx, ecx
0x1800494e1  lea     rax, [r9+38h]
0x1800494e5  lea     rdx, [r9+4]
0x1800494e9  mov     [rsp+340h+var_2F8], rdi
0x1800494ee  mov     [rsp+340h+var_300], rbx
0x1800494f3  mov     [rsp+340h+var_308], ecx
0x1800494f7  mov     [rsp+340h+var_310], rax
0x1800494fc  mov     eax, [rsp+340h+var_2F0]
0x180049500  mov     [rsp+340h+dwFlags], eax
0x180049504  mov     [rsp+340h+phHash], r12
0x180049509  mov     r9d, [r9+1Ch]
0x18004950d  mov     r8d, 14h
0x180049513  mov     rcx, [rsp+340h+hHash]
0x180049518  call    cs:__imp_?HashMessageProperties@@YAJ_KPEBEKK1KPEB_WKPEBUQUEUE_FORMAT@@3@Z; HashMessageProperties(unsigned __int64,uchar const *,ulong,ulong,uchar const *,ulong,wchar_t const *,ulong,QUEUE_FORMAT const *,QUEUE_FORMAT const *)
0x18004951e  mov     ebx, eax
0x180049520  test    eax, eax
0x180049522  jns     short loc_18004953D
0x180049524  mov     r8d, 3F2h; unsigned __int16
0x18004952a  lea     rdx, aQmsecutl; "qmsecutl"
0x180049531  mov     ecx, eax; int
0x180049533  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180049538  jmp     loc_18004987F
0x18004953d  xorps   xmm0, xmm0
0x180049540  movups  [rbp+240h+var_280], xmm0
0x180049544  movups  [rbp+240h+var_270], xmm0
0x180049548  xor     r8d, r8d; int
0x18004954b  lea     rdx, [rbp+240h+var_280]; struct QUEUE_FORMAT *
0x18004954f  mov     rcx, rsi; this
0x180049552  call    ?GetDestinationQueue@CQmPacket@@QEBAHPEAUQUEUE_FORMAT@@H@Z; CQmPacket::GetDestinationQueue(QUEUE_FORMAT *,int)
0x180049557  mov     [rsp+340h+var_2F0], 100h
0x18004955f  mov     [rsp+340h+var_2D8], 0
0x180049568  mov     [rsp+340h+Block], 0
0x180049571  lea     rax, [rsp+340h+var_2D8]
0x180049576  mov     [rsp+340h+phHash], rax; wchar_t **
0x18004957b  lea     r9, [rsp+340h+Block]; wchar_t **
0x180049580  lea     r8, [rsp+340h+var_2F0]; unsigned int *
0x180049585  lea     rdx, [rbp+240h+var_240]; wchar_t *
0x180049589  lea     rcx, [rbp+240h+var_280]; struct QUEUE_FORMAT *
0x18004958d  call    ?_GetDestinationFormatName@@YAJPEAUQUEUE_FORMAT@@PEA_WPEAKPEAPEA_W3@Z; _GetDestinationFormatName(QUEUE_FORMAT *,wchar_t *,ulong *,wchar_t * *,wchar_t * *)
0x180049592  mov     ebx, eax
0x180049594  test    eax, eax
0x180049596  jns     short loc_1800495BE
0x180049598  mov     r8d, 398h; unsigned __int16
0x18004959e  lea     rdx, aQmsecutl; "qmsecutl"
0x1800495a5  mov     ecx, eax; int
0x1800495a7  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x1800495ac  nop
0x1800495ad  mov     rcx, [rsp+340h+Block]; Block
0x1800495b2  call    cs:__imp_free
0x1800495b8  nop
0x1800495b9  jmp     loc_18004987F
0x1800495be  xor     eax, eax
0x1800495c0  mov     [rbp+240h+var_260], rax
0x1800495c4  mov     [rbp+240h+var_258], eax
0x1800495c7  mov     rdx, [rsi+30h]
0x1800495cb  mov     eax, [rdx+2Ch]
0x1800495ce  shr     eax, 5
0x1800495d1  and     al, 3
0x1800495d3  mov     byte ptr [rbp+240h+var_260], al
0x1800495d6  mov     rax, [rsi+28h]
0x1800495da  mov     cl, [rax+2]
0x1800495dd  and     cl, 7
0x1800495e0  mov     byte ptr [rbp+240h+var_260+1], cl
0x1800495e3  mov     eax, [rdx+2Ch]
0x1800495e6  shr     eax, 8
0x1800495e9  and     al, 3
0x1800495eb  mov     byte ptr [rbp+240h+var_260+2], al
0x1800495ee  mov     rcx, [rsi+48h]
0x1800495f2  mov     al, [rcx]
0x1800495f4  mov     byte ptr [rbp+240h+var_260+3], al
0x1800495f7  movzx   eax, word ptr [rcx+2]
0x1800495fb  mov     word ptr [rbp+240h+var_260+4], ax
0x1800495ff  mov     eax, [rcx+18h]
0x180049602  mov     [rbp+240h+var_258], eax
0x180049605  mov     ecx, 48h ; 'H'; unsigned __int64
0x18004960a  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18004960f  mov     rdi, rax
0x180049612  mov     [rsp+340h+var_2C8], rax
0x180049617  mov     dword ptr [rax], 3
0x18004961d  mov     ecx, [rsp+340h+var_2F0]
0x180049621  mov     [rax+8], ecx
0x180049624  mov     rcx, [rsp+340h+var_2D8]
0x180049629  mov     [rax+10h], rcx
0x18004962d  mov     r15d, 10h
0x180049633  mov     [rax+18h], r15d
0x180049637  mov     rcx, [rsi+30h]
0x18004963b  mov     [rax+20h], rcx
0x18004963f  mov     dword ptr [rax+28h], 0Ch
0x180049646  lea     rax, [rbp+240h+var_260]
0x18004964a  mov     [rdi+30h], rax
0x18004964e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180049655  movdqu  [rbp+240h+var_250], xmm0
0x18004965a  test    byte ptr [r14+6], 8
0x18004965f  jz      loc_1800496E8
0x180049665  lea     r12, [rbp+240h+var_250]
0x180049669  mov     r15, [rsi+30h]
0x18004966d  mov     ecx, [r15+2Ch]
0x180049671  bt      ecx, 16h
0x180049675  jnb     short loc_1800496D4
0x180049677  lea     r8, [r15+30h]; unsigned __int8 *
0x18004967b  mov     edx, ecx
0x18004967d  shr     edx, 0Ah
0x180049680  and     edx, 7; unsigned int
0x180049683  shr     ecx, 18h
0x180049686  and     cl, 1; bool
0x180049689  call    ?QueueSize@CUserHeader@@CAH_NKPEBEPEAE@Z; CUserHeader::QueueSize(bool,ulong,uchar const *,uchar *)
0x18004968e  movsxd  rbx, eax
0x180049691  lea     r8, [r15+30h]
0x180049695  add     r8, rbx; unsigned __int8 *
0x180049698  mov     edx, [r15+2Ch]
0x18004969c  shr     edx, 0Dh
0x18004969f  and     edx, 7; unsigned int
0x1800496a2  xor     ecx, ecx; bool
0x1800496a4  call    ?QueueSize@CUserHeader@@CAH_NKPEBEPEAE@Z; CUserHeader::QueueSize(bool,ulong,uchar const *,uchar *)
0x1800496a9  add     ebx, eax
0x1800496ab  movsxd  r8, ebx
0x1800496ae  add     r8, 30h ; '0'
0x1800496b2  add     r8, r15; unsigned __int8 *
0x1800496b5  movzx   edx, word ptr [r15+2Eh]
0x1800496ba  and     edx, 7; unsigned int
0x1800496bd  xor     ecx, ecx; bool
0x1800496bf  call    ?QueueSize@CUserHeader@@CAH_NKPEBEPEAE@Z; CUserHeader::QueueSize(bool,ulong,uchar const *,uchar *)
0x1800496c4  add     eax, ebx
0x1800496c6  movsxd  rcx, eax
0x1800496c9  add     rcx, 30h ; '0'
0x1800496cd  add     rcx, r15
0x1800496d0  cmovnz  r12, rcx
0x1800496d4  mov     r15d, 10h
0x1800496da  mov     [rdi+38h], r15d
0x1800496de  mov     [rdi+40h], r12
0x1800496e2  mov     dword ptr [rdi], 4
0x1800496e8  mov     rdx, rdi
0x1800496eb  mov     rcx, [rsp+340h+hHash]
0x1800496f0  call    cs:__imp_?MQSigHashMessageProperties@@YAJ_KPEAU_MsgHashData@@@Z; MQSigHashMessageProperties(unsigned __int64,_MsgHashData *)
0x1800496f6  mov     ebx, eax
0x1800496f8  test    eax, eax
0x1800496fa  jns     short loc_18004972C
0x1800496fc  mov     r8d, 406h; unsigned __int16
0x180049702  lea     rdx, aQmsecutl; "qmsecutl"
0x180049709  mov     ecx, eax; int
0x18004970b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180049710  nop
0x180049711  mov     rcx, rdi; Block
0x180049714  call    cs:__imp_free
0x18004971a  nop
0x18004971b  mov     rcx, [rsp+340h+Block]; Block
0x180049720  call    cs:__imp_free
0x180049726  nop
0x180049727  jmp     loc_18004987F
0x18004972c  movzx   r8d, word ptr [r14+4]
0x180049731  sub     r8d, 8; dwSigLen
0x180049735  lea     rdx, [r14+8]; pbSignature
0x180049739  mov     [rsp+340h+dwFlags], 0; dwFlags
0x180049741  mov     [rsp+340h+phHash], 0; szDescription
0x18004974a  mov     r9, [rsp+340h+hPubKey]; hPubKey
0x18004974f  mov     rcx, [rsp+340h+hHash]; hHash
0x180049754  call    cs:__imp_CryptVerifySignatureW
0x18004975a  test    eax, eax
0x18004975c  jnz     short loc_1800497D0
0x18004975e  call    cs:__imp_GetLastError
0x180049764  lea     rbx, WPP_GLOBAL_Control
0x18004976b  mov     rcx, cs:WPP_GLOBAL_Control
0x180049772  cmp     rcx, rbx
0x180049775  jz      short loc_18004979B
0x180049777  test    byte ptr [rcx+10Ch], 1
0x18004977e  jz      short loc_18004979B
0x180049780  mov     edx, 25h ; '%'
0x180049785  mov     r9d, eax
0x180049788  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x18004978f  mov     rcx, [rcx+100h]
0x180049796  call    WPP_SF_d
0x18004979b  mov     r8d, 477h; unsigned __int16
0x1800497a1  lea     rdx, aQmsecutl; "qmsecutl"
0x1800497a8  mov     ebx, 0C00E0082h
0x1800497ad  mov     ecx, ebx; int
0x1800497af  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800497b4  nop
0x1800497b5  mov     rcx, rdi; Block
0x1800497b8  call    cs:__imp_free
0x1800497be  nop
0x1800497bf  mov     rcx, [rsp+340h+Block]; Block
0x1800497c4  call    cs:__imp_free
0x1800497ca  nop
0x1800497cb  jmp     loc_18004987F
0x1800497d0  lea     rbx, WPP_GLOBAL_Control
0x1800497d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800497de  cmp     rcx, rbx
  ... truncated ...
```
