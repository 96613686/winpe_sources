# VerifySignature10

- ea: `0x180049000`
- end: `0x18004931b`
- name: `VerifySignature10`
- size: `795`
- prototype: `__int64 __fastcall(CQmPacket *this)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800498e8`
- `0x1800499e4`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x18002b19c`
- `0x18002c61c`
- `0x18002c6c8`
- `0x18003dcdc`
- `0x18003e314`
- `0x18003e3d8`
- `0x18003e56c`
- `0x18003e684`
- `0x180048958`
- `0x180049000`

## import_xrefs

- `ADVAPI32!CryptCreateHash` at `0x18004911c`
- `ADVAPI32!CryptCreateHash` at `0x18004911c`
- `ADVAPI32!CryptVerifySignatureW` at `0x180049221`
- `ADVAPI32!CryptVerifySignatureW` at `0x180049221`
- `KERNEL32!GetLastError` at `0x180049128`
- `KERNEL32!GetLastError` at `0x18004922b`
- `KERNEL32!GetLastError` at `0x180049128`
- `KERNEL32!GetLastError` at `0x18004922b`
- `mqsec!HashMessageProperties` at `0x1800491e3`
- `mqsec!HashMessageProperties` at `0x1800491e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VerifySignature10(CUserHeader **this, HCRYPTPROV a2, HCRYPTKEY a3, char a4)
{
  unsigned int v7; // r9d
  const BYTE *Signature; // r13
  CUserHeader *v10; // rdi
  unsigned __int8 *v11; // r9
  int v12; // ebx
  unsigned __int8 *v13; // r9
  int v14; // eax
  unsigned __int64 v15; // rdi
  const struct QUEUE_FORMAT *v16; // rbx
  DWORD LastError; // edi
  signed int v18; // ebx
  CUserHeader *v19; // r9
  const struct QUEUE_FORMAT *v20; // rcx
  int v21; // eax
  unsigned __int16 v22; // r8
  int v23; // ecx
  signed int v24; // eax
  PVOID *v25; // rcx
  CUserHeader *v26; // rax
  CUserHeader *v27; // rax
  __int16 v28; // ax
  unsigned __int8 v29; // dl
  DWORD dwSigLen; // [rsp+58h] [rbp-29h] BYREF
  unsigned int v31; // [rsp+5Ch] [rbp-25h] BYREF
  HCRYPTHASH hHash; // [rsp+60h] [rbp-21h] BYREF
  const unsigned __int8 *PacketBody; // [rsp+68h] [rbp-19h]
  _OWORD v34[2]; // [rsp+70h] [rbp-11h] BYREF
  _OWORD v35[2]; // [rsp+90h] [rbp+Fh] BYREF

  dwSigLen = 0;
  Signature = CQmPacket::GetSignature((CQmPacket *)this, (unsigned __int16 *)&dwSigLen);
  if ( dwSigLen == v7 )
    return 0;
  v31 = v7;
  PacketBody = CQmPacket::GetPacketBody((CQmPacket *)this, &v31);
  memset(v34, 0, sizeof(v34));
  v10 = this[6];
  v12 = CUserHeader::QueueSize(
          *((_DWORD *)v10 + 11) & 0x1000000,
          (*((_DWORD *)v10 + 11) >> 10) & 7,
          (const unsigned __int8 *)v10 + 48,
          v11);
  v14 = CUserHeader::QueueSize(
          0,
          (unsigned __int8)HIBYTE(*((_WORD *)v10 + 22)) >> 5,
          (const unsigned __int8 *)v10 + v12 + 48,
          v13);
  v15 = (unsigned __int64)v34
      & -(__int64)((unsigned int)CUserHeader::GetQueue(
                                   v10,
                                   (const unsigned __int8 *)v10 + v12 + v14 + 48,
                                   0,
                                   *((_WORD *)v10 + 23) & 7,
                                   (struct QUEUE_FORMAT *)v34) != 0);
  memset(v35, 0, sizeof(v35));
  v16 = (const struct QUEUE_FORMAT *)((unsigned __int64)v35
                                    & -(__int64)((unsigned int)CUserHeader::GetAdminQueue(
                                                                 this[6],
                                                                 (struct QUEUE_FORMAT *)v35) != 0));
  hHash = 0;
  if ( !CryptCreateHash(a2, *((_DWORD *)this[9] + 11), 0, 0, &hHash) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 33, WPP_c687450366573ca356992ecf9dac13b8_Traceguids, LastError);
    if ( LastError )
      LogMsgNTStatus(LastError, (wchar_t *)L"qmsecutl", 0xEBu);
    v18 = -1072824272;
    goto LABEL_37;
  }
  v19 = this[9];
  if ( *((_WORD *)v19 + 1) )
  {
    v20 = (const struct QUEUE_FORMAT *)v15;
  }
  else
  {
    v20 = v16;
    v16 = (const struct QUEUE_FORMAT *)v15;
  }
  v21 = HashMessageProperties(
          hHash,
          (const unsigned __int8 *)v19 + 4,
          0x14u,
          *((_DWORD *)v19 + 7),
          PacketBody,
          v31,
          (const wchar_t *)v19 + 28,
          2 * *((unsigned __int8 *)v19 + 1),
          v16,
          v20);
  v18 = v21;
  if ( v21 < 0 )
  {
    v22 = 240;
    v23 = v21;
LABEL_15:
    LogMsgHR(v23, (wchar_t *)L"qmsecutl", v22);
    goto LABEL_37;
  }
  if ( CryptVerifySignatureW(hHash, Signature, dwSigLen, a3, 0, 0) )
  {
    v25 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 34, WPP_c687450366573ca356992ecf9dac13b8_Traceguids);
      v25 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( a4 )
    {
      v26 = this[8];
      if ( v26 )
        *(_WORD *)v26 |= 0x10u;
      v27 = this[8];
      if ( v27 )
        v28 = *(_WORD *)v27 & 0xF;
      else
        v28 = 0;
      v29 = 11;
      if ( v28 != 2 )
        v29 = 1;
      CQmPacket::SetLevelOfAuthentication((CQmPacket *)this, v29);
    }
    else if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 268) & 4) != 0 )
    {
      WPP_SF_(v25[32], 35, WPP_c687450366573ca356992ecf9dac13b8_Traceguids);
    }
    v18 = 0;
    goto LABEL_37;
  }
  v24 = GetLastError();
  v18 = v24;
  if ( v24 > 0 )
    v18 = (unsigned __int16)v24 | 0x80070000;
  if ( v18 < 0 )
  {
    v22 = 242;
    v23 = v18;
    goto LABEL_15;
  }
LABEL_37:
  CHashHandle::~CHashHandle((CHashHandle *)&hHash);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180049000  mov     rax, rsp
0x180049003  mov     [rax+8], rbx
0x180049007  mov     [rax+18h], rsi
0x18004900b  mov     [rax+10h], rdx
0x18004900f  push    rbp
0x180049010  push    rdi
0x180049011  push    r12
0x180049013  push    r13
0x180049015  push    r15
0x180049017  lea     rbp, [rax-5Fh]
0x18004901b  sub     rsp, 0B0h
0x180049022  mov     r15b, r9b
0x180049025  mov     r12, r8
0x180049028  mov     rsi, rcx
0x18004902b  xor     r9d, r9d
0x18004902e  mov     [rbp+57h+dwSigLen], r9d
0x180049032  lea     rdx, [rbp+57h+dwSigLen]; unsigned __int16 *
0x180049036  call    ?GetSignature@CQmPacket@@QEBAPEBEPEAG@Z; CQmPacket::GetSignature(ushort *)
0x18004903b  mov     r13, rax
0x18004903e  cmp     [rbp+57h+dwSigLen], r9d
0x180049042  jnz     short loc_18004904B
0x180049044  xor     eax, eax
0x180049046  jmp     loc_1800492FF
0x18004904b  mov     [rbp+57h+var_7C], r9d
0x18004904f  lea     rdx, [rbp+57h+var_7C]; unsigned int *
0x180049053  mov     rcx, rsi; this
0x180049056  call    ?GetPacketBody@CQmPacket@@QEBAPEBEPEAK@Z; CQmPacket::GetPacketBody(ulong *)
0x18004905b  mov     [rbp+57h+var_70], rax
0x18004905f  xorps   xmm0, xmm0
0x180049062  movups  [rbp+57h+var_68], xmm0
0x180049066  movups  [rbp+57h+var_58], xmm0
0x18004906a  mov     rdi, [rsi+30h]
0x18004906e  mov     ecx, [rdi+2Ch]
0x180049071  lea     r8, [rdi+30h]; unsigned __int8 *
0x180049075  mov     edx, ecx
0x180049077  shr     edx, 0Ah
0x18004907a  and     edx, 7; unsigned int
0x18004907d  shr     ecx, 18h
0x180049080  and     cl, 1; bool
0x180049083  call    ?QueueSize@CUserHeader@@CAH_NKPEBEPEAE@Z; CUserHeader::QueueSize(bool,ulong,uchar const *,uchar *)
0x180049088  movsxd  rbx, eax
0x18004908b  lea     r8, [rdi+30h]
0x18004908f  add     r8, rbx; unsigned __int8 *
0x180049092  mov     edx, [rdi+2Ch]
0x180049095  shr     edx, 0Dh
0x180049098  and     edx, 7; unsigned int
0x18004909b  xor     ecx, ecx; bool
0x18004909d  call    ?QueueSize@CUserHeader@@CAH_NKPEBEPEAE@Z; CUserHeader::QueueSize(bool,ulong,uchar const *,uchar *)
0x1800490a2  add     eax, ebx
0x1800490a4  movzx   r9d, word ptr [rdi+2Eh]
0x1800490a9  and     r9d, 7; unsigned int
0x1800490ad  cdqe
0x1800490af  lea     rdx, [rdi+30h]
0x1800490b3  add     rdx, rax; unsigned __int8 *
0x1800490b6  lea     rax, [rbp+57h+var_68]
0x1800490ba  mov     [rsp+0D0h+phHash], rax; struct QUEUE_FORMAT *
0x1800490bf  xor     r8d, r8d; bool
0x1800490c2  mov     rcx, rdi; this
0x1800490c5  call    ?GetQueue@CUserHeader@@AEBAHPEBE_NKPEAUQUEUE_FORMAT@@@Z; CUserHeader::GetQueue(uchar const *,bool,ulong,QUEUE_FORMAT *)
0x1800490ca  neg     eax
0x1800490cc  sbb     rdi, rdi
0x1800490cf  lea     rax, [rbp+57h+var_68]
0x1800490d3  and     rdi, rax
0x1800490d6  xorps   xmm0, xmm0
0x1800490d9  movups  [rbp+57h+var_48], xmm0
0x1800490dd  movups  [rbp+57h+var_38], xmm0
0x1800490e1  lea     rdx, [rbp+57h+var_48]; struct QUEUE_FORMAT *
0x1800490e5  mov     rcx, [rsi+30h]; this
0x1800490e9  call    ?GetAdminQueue@CUserHeader@@QEBAHPEAUQUEUE_FORMAT@@@Z; CUserHeader::GetAdminQueue(QUEUE_FORMAT *)
0x1800490ee  neg     eax
0x1800490f0  sbb     rbx, rbx
0x1800490f3  lea     rax, [rbp+57h+var_48]
0x1800490f7  and     rbx, rax
0x1800490fa  mov     [rbp+57h+hHash], 0
0x180049102  mov     rdx, [rsi+48h]
0x180049106  lea     rax, [rbp+57h+hHash]
0x18004910a  mov     [rsp+0D0h+phHash], rax; phHash
0x18004910f  xor     r9d, r9d; dwFlags
0x180049112  xor     r8d, r8d; hKey
0x180049115  mov     edx, [rdx+2Ch]; Algid
0x180049118  mov     rcx, [rbp+57h+hProv]; hProv
0x18004911c  call    cs:__imp_CryptCreateHash
0x180049122  xor     ecx, ecx
0x180049124  test    eax, eax
0x180049126  jnz     short loc_18004918B
0x180049128  call    cs:__imp_GetLastError
0x18004912e  mov     edi, eax
0x180049130  lea     rbx, WPP_GLOBAL_Control
0x180049137  mov     rcx, cs:WPP_GLOBAL_Control
0x18004913e  cmp     rcx, rbx
0x180049141  jz      short loc_180049169
0x180049143  mov     eax, 1
0x180049148  test    [rcx+10Ch], al
0x18004914e  jz      short loc_180049169
0x180049150  lea     edx, [rax+20h]
0x180049153  mov     r9d, edi
0x180049156  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x18004915d  mov     rcx, [rcx+100h]
0x180049164  call    WPP_SF_d
0x180049169  test    edi, edi
0x18004916b  jz      short loc_180049181
0x18004916d  mov     r8d, 0EBh; unsigned __int16
0x180049173  lea     rdx, aQmsecutl; "qmsecutl"
0x18004917a  mov     ecx, edi; int
0x18004917c  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180049181  mov     ebx, 0C00E0030h
0x180049186  jmp     loc_1800492F4
0x18004918b  mov     r9, [rsi+48h]
0x18004918f  cmp     [r9+2], cx
0x180049194  jz      short loc_18004919B
0x180049196  mov     rcx, rdi
0x180049199  jmp     short loc_1800491A1
0x18004919b  mov     rcx, rbx
0x18004919e  mov     rbx, rdi
0x1800491a1  movzx   r8d, byte ptr [r9+1]
0x1800491a6  add     r8d, r8d
0x1800491a9  lea     rax, [r9+38h]
0x1800491ad  lea     rdx, [r9+4]
0x1800491b1  mov     [rsp+0D0h+var_88], rcx
0x1800491b6  mov     [rsp+0D0h+var_90], rbx
0x1800491bb  mov     dword ptr [rsp+0D0h+var_98], r8d
0x1800491c0  mov     qword ptr [rsp+0D0h+var_A0], rax
0x1800491c5  mov     eax, [rbp+57h+var_7C]
0x1800491c8  mov     [rsp+0D0h+dwFlags], eax
0x1800491cc  mov     rax, [rbp+57h+var_70]
0x1800491d0  mov     [rsp+0D0h+phHash], rax
0x1800491d5  mov     r9d, [r9+1Ch]
0x1800491d9  mov     r8d, 14h
0x1800491df  mov     rcx, [rbp+57h+hHash]
0x1800491e3  call    cs:__imp_?HashMessageProperties@@YAJ_KPEBEKK1KPEB_WKPEBUQUEUE_FORMAT@@3@Z; HashMessageProperties(unsigned __int64,uchar const *,ulong,ulong,uchar const *,ulong,wchar_t const *,ulong,QUEUE_FORMAT const *,QUEUE_FORMAT const *)
0x1800491e9  mov     ebx, eax
0x1800491eb  xor     edi, edi
0x1800491ed  test    eax, eax
0x1800491ef  jns     short loc_18004920A
0x1800491f1  mov     r8d, 0F0h; unsigned __int16
0x1800491f7  mov     ecx, eax; int
0x1800491f9  lea     rdx, aQmsecutl; "qmsecutl"
0x180049200  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180049205  jmp     loc_1800492F4
0x18004920a  mov     [rsp+0D0h+dwFlags], edi; dwFlags
0x18004920e  mov     [rsp+0D0h+phHash], rdi; szDescription
0x180049213  mov     r9, r12; hPubKey
0x180049216  mov     r8d, [rbp+57h+dwSigLen]; dwSigLen
0x18004921a  mov     rdx, r13; pbSignature
0x18004921d  mov     rcx, [rbp+57h+hHash]; hHash
0x180049221  call    cs:__imp_CryptVerifySignatureW
0x180049227  test    eax, eax
0x180049229  jnz     short loc_180049252
0x18004922b  call    cs:__imp_GetLastError
0x180049231  mov     ebx, eax
0x180049233  test    eax, eax
0x180049235  jle     short loc_180049240
0x180049237  movzx   ebx, ax
0x18004923a  or      ebx, 80070000h
0x180049240  test    ebx, ebx
0x180049242  jns     loc_1800492F4
0x180049248  mov     r8d, 0F2h
0x18004924e  mov     ecx, ebx
0x180049250  jmp     short loc_1800491F9
0x180049252  lea     rbx, WPP_GLOBAL_Control
0x180049259  mov     rcx, cs:WPP_GLOBAL_Control
0x180049260  cmp     rcx, rbx
0x180049263  jz      short loc_18004928D
0x180049265  test    byte ptr [rcx+10Ch], 4
0x18004926c  jz      short loc_18004928D
0x18004926e  mov     edx, 22h ; '"'
0x180049273  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x18004927a  mov     rcx, [rcx+100h]
0x180049281  call    WPP_SF_
0x180049286  mov     rcx, cs:WPP_GLOBAL_Control
0x18004928d  test    r15b, r15b
0x180049290  jz      short loc_1800492CC
0x180049292  mov     rax, [rsi+40h]
0x180049296  test    rax, rax
0x180049299  jz      short loc_18004929F
0x18004929b  or      word ptr [rax], 10h
0x18004929f  mov     rax, [rsi+40h]
0x1800492a3  test    rax, rax
0x1800492a6  jz      short loc_1800492B1
0x1800492a8  movzx   eax, word ptr [rax]
0x1800492ab  and     ax, 0Fh
0x1800492af  jmp     short loc_1800492B3
0x1800492b1  mov     eax, edi
0x1800492b3  mov     edx, 0Bh
0x1800492b8  cmp     ax, 2
0x1800492bc  lea     eax, [rdx-0Ah]
0x1800492bf  cmovnz  edx, eax; unsigned __int8
0x1800492c2  mov     rcx, rsi; this
0x1800492c5  call    ?SetLevelOfAuthentication@CQmPacket@@QEAAXE@Z; CQmPacket::SetLevelOfAuthentication(uchar)
0x1800492ca  jmp     short loc_1800492F2
0x1800492cc  cmp     rcx, rbx
0x1800492cf  jz      short loc_1800492F2
0x1800492d1  test    byte ptr [rcx+10Ch], 4
0x1800492d8  jz      short loc_1800492F2
0x1800492da  mov     edx, 23h ; '#'
0x1800492df  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x1800492e6  mov     rcx, [rcx+100h]
0x1800492ed  call    WPP_SF_
0x1800492f2  mov     ebx, edi
0x1800492f4  lea     rcx, [rbp+57h+hHash]; this
0x1800492f8  call    ??1CHashHandle@@QEAA@XZ; CHashHandle::~CHashHandle(void)
0x1800492fd  mov     eax, ebx
0x1800492ff  lea     r11, [rsp+0D0h+var_20]
0x180049307  mov     rbx, [r11+30h]
0x18004930b  mov     rsi, [r11+40h]
0x18004930f  mov     rsp, r11
0x180049312  pop     r15
0x180049314  pop     r13
0x180049316  pop     r12
0x180049318  pop     rdi
0x180049319  pop     rbp
0x18004931a  retn
```
