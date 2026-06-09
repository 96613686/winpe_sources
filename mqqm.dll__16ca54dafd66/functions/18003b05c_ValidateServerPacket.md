# ValidateServerPacket

- ea: `0x18003b05c`
- end: `0x18003b511`
- name: `ValidateServerPacket`
- size: `1205`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003a310`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x18002b19c`
- `0x18002c574`
- `0x18002c61c`
- `0x18002c6c8`
- `0x180039548`
- `0x18003b05c`
- `0x1800950b0`

## import_xrefs

- `ADVAPI32!CryptCreateHash` at `0x18003b159`
- `ADVAPI32!CryptCreateHash` at `0x18003b159`
- `ADVAPI32!CryptGetUserKey` at `0x18003b287`
- `ADVAPI32!CryptGetUserKey` at `0x18003b287`
- `ADVAPI32!CryptVerifySignatureW` at `0x18003b320`
- `ADVAPI32!CryptVerifySignatureW` at `0x18003b320`
- `KERNEL32!GetLastError` at `0x18003b163`
- `KERNEL32!GetLastError` at `0x18003b291`
- `KERNEL32!GetLastError` at `0x18003b32a`
- `KERNEL32!GetLastError` at `0x18003b163`
- `KERNEL32!GetLastError` at `0x18003b291`
- `KERNEL32!GetLastError` at `0x18003b32a`
- `mqsec!HashMessageProperties` at `0x18003b21f`
- `mqsec!HashMessageProperties` at `0x18003b21f`
- `mqsec!MQSec_AcquireCryptoProvider` at `0x18003b0d7`
- `mqsec!MQSec_AcquireCryptoProvider` at `0x18003b0d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ValidateServerPacket(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v4; // rcx
  _DWORD *v5; // r9
  __int64 v6; // rax
  int v7; // esi
  signed int v8; // edi
  bool v9; // sf
  unsigned __int16 v10; // r8
  int v11; // esi
  signed int LastError; // edi
  bool v13; // sf
  DWORD v14; // edi
  int v15; // edi
  unsigned __int16 v16; // r8
  HCRYPTPROV hProv; // [rsp+50h] [rbp-20h] BYREF
  __int128 v19; // [rsp+58h] [rbp-18h] BYREF
  __int64 v20; // [rsp+68h] [rbp-8h]
  int v21; // [rsp+90h] [rbp+20h] BYREF
  HCRYPTHASH hHash; // [rsp+A0h] [rbp+30h] BYREF
  HCRYPTKEY phUserKey; // [rsp+A8h] [rbp+38h] BYREF

  v4 = *(_QWORD **)(a1 + 96);
  v5 = (_DWORD *)(a1 + 136);
  if ( !v4 || *v5 != 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids,
        (unsigned int)*v5);
    v16 = 1201;
    goto LABEL_66;
  }
  if ( *(_BYTE *)(a1 + 148) )
  {
LABEL_46:
    v21 = 210;
    v19 = 0;
    v20 = 0;
    LOWORD(v19) = 19;
    v15 = ADGetObjectPropertiesGuid(1, 0, a3, *(_QWORD *)(a1 + 96), 1, &v21, &v19);
    if ( v15 >= 0 )
    {
      if ( ((DWORD2(v19) - 2) & 0xFFFFFFF9) == 0 && DWORD2(v19) != 6 )
        return 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids, DWORD2(v19));
      v16 = 1220;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids,
          (unsigned int)v15);
      LogMsgHR(v15, (wchar_t *)L"qmnotify", 0x4C2u);
      v16 = 1219;
    }
    goto LABEL_66;
  }
  if ( !*(_QWORD *)(a1 + 168) )
    goto LABEL_52;
  v6 = *v4 - *a2;
  if ( *v4 == *a2 )
    v6 = v4[1] - a2[1];
  if ( v6 )
  {
LABEL_52:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids);
    v16 = 1202;
LABEL_66:
    LogMsgBOOL(0, (wchar_t *)L"qmnotify", v16);
    return 0;
  }
  hHash = 0;
  phUserKey = 0;
  hProv = 0;
  v7 = MQSec_AcquireCryptoProvider(1, &hProv);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids,
        (unsigned int)v7);
    LogMsgHR(v7, (wchar_t *)L"qmnotify", 0x4B3u);
    goto LABEL_13;
  }
  if ( CryptCreateHash(hProv, *(_DWORD *)(a1 + 128), 0, 0, &hHash) )
  {
    v11 = HashMessageProperties(
            hHash,
            *(const unsigned __int8 **)(a1 + 24),
            0x14u,
            *(_DWORD *)(a1 + 40),
            *(const unsigned __int8 **)(a1 + 80),
            *(_DWORD *)(a1 + 72),
            *(const wchar_t **)(a1 + 48),
            2 * *(_DWORD *)(a1 + 44),
            0,
            0);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids,
          (unsigned int)v11);
      LogMsgHR(v11, (wchar_t *)L"qmnotify", 0x4BCu);
      v10 = 1213;
      goto LABEL_23;
    }
    if ( !CryptGetUserKey(hProv, 2u, &phUserKey) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids,
          (unsigned int)LastError);
      v13 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v13 = LastError < 0;
      }
      if ( v13 )
        LogMsgHR(LastError, (wchar_t *)L"qmnotify", 0x4BEu);
      v10 = 1215;
      goto LABEL_23;
    }
    if ( !CryptVerifySignatureW(hHash, *(const BYTE **)(a1 + 168), *(_DWORD *)(a1 + 176), phUserKey, 0, 0) )
    {
      v14 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids, v14);
      if ( v14 )
        LogMsgNTStatus(v14, (wchar_t *)L"qmnotify", 0x4C0u);
      v10 = 1217;
      goto LABEL_23;
    }
    CHCryptKey::~CHCryptKey((CHCryptKey *)&phUserKey);
    CHashHandle::~CHashHandle((CHashHandle *)&hHash);
    goto LABEL_46;
  }
  v8 = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids,
      (unsigned int)v8);
  v9 = v8 < 0;
  if ( v8 > 0 )
  {
    v8 = (unsigned __int16)v8 | 0x80070000;
    v9 = v8 < 0;
  }
  if ( v9 )
    LogMsgHR(v8, (wchar_t *)L"qmnotify", 0x4BAu);
  v10 = 1211;
LABEL_23:
  LogMsgBOOL(0, (wchar_t *)L"qmnotify", v10);
LABEL_13:
  CHCryptKey::~CHCryptKey((CHCryptKey *)&phUserKey);
  CHashHandle::~CHashHandle((CHashHandle *)&hHash);
  return 0;
}

```

## disassembly

```asm
0x18003b05c  mov     [rsp-18h+arg_8], rbx
0x18003b061  push    rbp
0x18003b062  push    rsi
0x18003b063  push    rdi
0x18003b064  mov     rbp, rsp
0x18003b067  sub     rsp, 70h
0x18003b06b  mov     rdi, rcx
0x18003b06e  mov     rcx, [rcx+60h]
0x18003b072  lea     r9, [rdi+88h]
0x18003b079  test    rcx, rcx
0x18003b07c  jz      loc_18003B4B8
0x18003b082  cmp     dword ptr [r9], 2
0x18003b086  jnz     loc_18003B4B8
0x18003b08c  mov     ebx, 1
0x18003b091  cmp     byte ptr [rdi+94h], 0
0x18003b098  jnz     loc_18003B398
0x18003b09e  cmp     qword ptr [rdi+0A8h], 0
0x18003b0a6  jz      loc_18003B431
0x18003b0ac  mov     rax, [rcx]
0x18003b0af  sub     rax, [rdx]
0x18003b0b2  jnz     short loc_18003B0BC
0x18003b0b4  mov     rax, [rcx+8]
0x18003b0b8  sub     rax, [rdx+8]
0x18003b0bc  test    rax, rax
0x18003b0bf  jnz     loc_18003B431
0x18003b0c5  mov     [rbp+hHash], rax
0x18003b0c9  mov     [rbp+phUserKey], rax
0x18003b0cd  mov     [rbp+hProv], rax
0x18003b0d1  lea     rdx, [rbp+hProv]
0x18003b0d5  mov     ecx, ebx
0x18003b0d7  call    cs:__imp_?MQSec_AcquireCryptoProvider@@YAJW4enumProvider@@PEA_K@Z; MQSec_AcquireCryptoProvider(enumProvider,unsigned __int64 *)
0x18003b0dd  mov     esi, eax
0x18003b0df  test    eax, eax
0x18003b0e1  jns     short loc_18003B140
0x18003b0e3  lea     rax, WPP_GLOBAL_Control
0x18003b0ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b0f1  cmp     rcx, rax
0x18003b0f4  jz      short loc_18003B113
0x18003b0f6  test    [rcx+1Ch], bl
0x18003b0f9  jz      short loc_18003B113
0x18003b0fb  mov     edx, 2Dh ; '-'
0x18003b100  mov     r9d, esi
0x18003b103  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003b10a  mov     rcx, [rcx+10h]
0x18003b10e  call    WPP_SF_d
0x18003b113  mov     r8d, 4B3h; unsigned __int16
0x18003b119  lea     rdx, aQmnotify; "qmnotify"
0x18003b120  mov     ecx, esi; int
0x18003b122  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18003b127  nop
0x18003b128  lea     rcx, [rbp+phUserKey]; this
0x18003b12c  call    ??1CHCryptKey@@QEAA@XZ; CHCryptKey::~CHCryptKey(void)
0x18003b131  nop
0x18003b132  lea     rcx, [rbp+hHash]; this
0x18003b136  call    ??1CHashHandle@@QEAA@XZ; CHashHandle::~CHashHandle(void)
0x18003b13b  jmp     loc_18003B4FF
0x18003b140  lea     rax, [rbp+hHash]
0x18003b144  mov     [rsp+70h+phHash], rax; phHash
0x18003b149  xor     r9d, r9d; dwFlags
0x18003b14c  xor     r8d, r8d; hKey
0x18003b14f  mov     edx, [rdi+80h]; Algid
0x18003b155  mov     rcx, [rbp+hProv]; hProv
0x18003b159  call    cs:__imp_CryptCreateHash
0x18003b15f  test    eax, eax
0x18003b161  jnz     short loc_18003B1D9
0x18003b163  call    cs:__imp_GetLastError
0x18003b169  mov     edi, eax
0x18003b16b  lea     rax, WPP_GLOBAL_Control
0x18003b172  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b179  cmp     rcx, rax
0x18003b17c  jz      short loc_18003B19B
0x18003b17e  test    [rcx+1Ch], bl
0x18003b181  jz      short loc_18003B19B
0x18003b183  mov     edx, 2Eh ; '.'
0x18003b188  mov     r9d, edi
0x18003b18b  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003b192  mov     rcx, [rcx+10h]
0x18003b196  call    WPP_SF_d
0x18003b19b  test    edi, edi
0x18003b19d  jle     short loc_18003B1AA
0x18003b19f  movzx   edi, di
0x18003b1a2  or      edi, 80070000h
0x18003b1a8  test    edi, edi
0x18003b1aa  jns     short loc_18003B1C0
0x18003b1ac  mov     r8d, 4BAh; unsigned __int16
0x18003b1b2  lea     rdx, aQmnotify; "qmnotify"
0x18003b1b9  mov     ecx, edi; int
0x18003b1bb  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18003b1c0  mov     r8d, 4BBh; unsigned __int16
0x18003b1c6  lea     rdx, aQmnotify; "qmnotify"
0x18003b1cd  xor     ecx, ecx; int
0x18003b1cf  call    ?LogMsgBOOL@@YAXHPEA_WG@Z; LogMsgBOOL(int,wchar_t *,ushort)
0x18003b1d4  jmp     loc_18003B128
0x18003b1d9  mov     eax, [rdi+2Ch]
0x18003b1dc  add     eax, eax
0x18003b1de  mov     [rsp+70h+var_28], 0
0x18003b1e7  mov     [rsp+70h+var_30], 0
0x18003b1f0  mov     [rsp+70h+var_38], eax
0x18003b1f4  mov     rax, [rdi+30h]
0x18003b1f8  mov     [rsp+70h+var_40], rax
0x18003b1fd  mov     eax, [rdi+48h]
0x18003b200  mov     [rsp+70h+dwFlags], eax
0x18003b204  mov     rax, [rdi+50h]
0x18003b208  mov     [rsp+70h+phHash], rax
0x18003b20d  mov     r9d, [rdi+28h]
0x18003b211  mov     r8d, 14h
0x18003b217  mov     rdx, [rdi+18h]
0x18003b21b  mov     rcx, [rbp+hHash]
0x18003b21f  call    cs:__imp_?HashMessageProperties@@YAJ_KPEBEKK1KPEB_WKPEBUQUEUE_FORMAT@@3@Z; HashMessageProperties(unsigned __int64,uchar const *,ulong,ulong,uchar const *,ulong,wchar_t const *,ulong,QUEUE_FORMAT const *,QUEUE_FORMAT const *)
0x18003b225  mov     esi, eax
0x18003b227  test    eax, eax
0x18003b229  jns     short loc_18003B27A
0x18003b22b  lea     rax, WPP_GLOBAL_Control
0x18003b232  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b239  cmp     rcx, rax
0x18003b23c  jz      short loc_18003B25B
0x18003b23e  test    [rcx+1Ch], bl
0x18003b241  jz      short loc_18003B25B
0x18003b243  mov     edx, 2Fh ; '/'
0x18003b248  mov     r9d, esi
0x18003b24b  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003b252  mov     rcx, [rcx+10h]
0x18003b256  call    WPP_SF_d
0x18003b25b  mov     r8d, 4BCh; unsigned __int16
0x18003b261  lea     rdx, aQmnotify; "qmnotify"
0x18003b268  mov     ecx, esi; int
0x18003b26a  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18003b26f  mov     r8d, 4BDh
0x18003b275  jmp     loc_18003B1C6
0x18003b27a  lea     r8, [rbp+phUserKey]; phUserKey
0x18003b27e  mov     edx, 2; dwKeySpec
0x18003b283  mov     rcx, [rbp+hProv]; hProv
0x18003b287  call    cs:__imp_CryptGetUserKey
0x18003b28d  test    eax, eax
0x18003b28f  jnz     short loc_18003B2F9
0x18003b291  call    cs:__imp_GetLastError
0x18003b297  mov     edi, eax
0x18003b299  lea     rax, WPP_GLOBAL_Control
0x18003b2a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b2a7  cmp     rcx, rax
0x18003b2aa  jz      short loc_18003B2C9
0x18003b2ac  test    [rcx+1Ch], bl
0x18003b2af  jz      short loc_18003B2C9
0x18003b2b1  mov     edx, 30h ; '0'
0x18003b2b6  mov     r9d, edi
0x18003b2b9  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003b2c0  mov     rcx, [rcx+10h]
0x18003b2c4  call    WPP_SF_d
0x18003b2c9  test    edi, edi
0x18003b2cb  jle     short loc_18003B2D8
0x18003b2cd  movzx   edi, di
0x18003b2d0  or      edi, 80070000h
0x18003b2d6  test    edi, edi
0x18003b2d8  jns     short loc_18003B2EE
0x18003b2da  mov     r8d, 4BEh; unsigned __int16
0x18003b2e0  lea     rdx, aQmnotify; "qmnotify"
0x18003b2e7  mov     ecx, edi; int
0x18003b2e9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18003b2ee  mov     r8d, 4BFh
0x18003b2f4  jmp     loc_18003B1C6
0x18003b2f9  mov     [rsp+70h+dwFlags], 0; dwFlags
0x18003b301  mov     [rsp+70h+phHash], 0; szDescription
0x18003b30a  mov     r9, [rbp+phUserKey]; hPubKey
0x18003b30e  mov     r8d, [rdi+0B0h]; dwSigLen
0x18003b315  mov     rdx, [rdi+0A8h]; pbSignature
0x18003b31c  mov     rcx, [rbp+hHash]; hHash
0x18003b320  call    cs:__imp_CryptVerifySignatureW
0x18003b326  test    eax, eax
0x18003b328  jnz     short loc_18003B385
0x18003b32a  call    cs:__imp_GetLastError
0x18003b330  mov     edi, eax
0x18003b332  lea     rax, WPP_GLOBAL_Control
0x18003b339  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b340  cmp     rcx, rax
0x18003b343  jz      short loc_18003B362
0x18003b345  test    [rcx+1Ch], bl
0x18003b348  jz      short loc_18003B362
0x18003b34a  mov     edx, 31h ; '1'
0x18003b34f  mov     r9d, edi
0x18003b352  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003b359  mov     rcx, [rcx+10h]
0x18003b35d  call    WPP_SF_d
0x18003b362  test    edi, edi
0x18003b364  jz      short loc_18003B37A
0x18003b366  mov     r8d, 4C0h; unsigned __int16
0x18003b36c  lea     rdx, aQmnotify; "qmnotify"
0x18003b373  mov     ecx, edi; int
0x18003b375  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18003b37a  mov     r8d, 4C1h
0x18003b380  jmp     loc_18003B1C6
0x18003b385  lea     rcx, [rbp+phUserKey]; this
0x18003b389  call    ??1CHCryptKey@@QEAA@XZ; CHCryptKey::~CHCryptKey(void)
0x18003b38e  nop
0x18003b38f  lea     rcx, [rbp+hHash]; this
0x18003b393  call    ??1CHashHandle@@QEAA@XZ; CHashHandle::~CHashHandle(void)
0x18003b398  mov     [rbp+arg_0], 0D2h
0x18003b39f  xorps   xmm0, xmm0
0x18003b3a2  xor     eax, eax
0x18003b3a4  movups  [rbp+var_18], xmm0
0x18003b3a8  mov     [rbp+var_8], rax
0x18003b3ac  mov     eax, 13h
0x18003b3b1  mov     word ptr [rbp+var_18], ax
0x18003b3b5  lea     rax, [rbp+var_18]
0x18003b3b9  mov     [rsp+70h+var_40], rax
0x18003b3be  lea     rax, [rbp+arg_0]
0x18003b3c2  mov     qword ptr [rsp+70h+dwFlags], rax
0x18003b3c7  mov     dword ptr [rsp+70h+phHash], ebx
0x18003b3cb  mov     r9, [rdi+60h]
0x18003b3cf  xor     edx, edx
0x18003b3d1  mov     ecx, ebx
0x18003b3d3  call    ?ADGetObjectPropertiesGuid@@YAJW4AD_OBJECT@@PEB_W_NPEBU_GUID@@KQEBKQEAUtagPROPVARIANT@@@Z; ADGetObjectPropertiesGuid(AD_OBJECT,wchar_t const *,bool,_GUID const *,ulong,ulong const * const,tagPROPVARIANT * const)
0x18003b3d8  mov     edi, eax
0x18003b3da  test    eax, eax
0x18003b3dc  jns     loc_18003B469
0x18003b3e2  lea     rax, WPP_GLOBAL_Control
0x18003b3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3f0  cmp     rcx, rax
0x18003b3f3  jz      short loc_18003B412
0x18003b3f5  test    [rcx+1Ch], bl
0x18003b3f8  jz      short loc_18003B412
0x18003b3fa  mov     edx, 32h ; '2'
0x18003b3ff  mov     r9d, edi
0x18003b402  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003b409  mov     rcx, [rcx+10h]
0x18003b40d  call    WPP_SF_d
0x18003b412  mov     r8d, 4C2h; unsigned __int16
0x18003b418  lea     rdx, aQmnotify; "qmnotify"
0x18003b41f  mov     ecx, edi; int
0x18003b421  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18003b426  mov     r8d, 4C3h
0x18003b42c  jmp     loc_18003B4F1
0x18003b431  lea     rax, WPP_GLOBAL_Control
0x18003b438  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b43f  cmp     rcx, rax
0x18003b442  jz      short loc_18003B45E
0x18003b444  test    [rcx+1Ch], bl
0x18003b447  jz      short loc_18003B45E
0x18003b449  mov     edx, 2Ch ; ','
0x18003b44e  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003b455  mov     rcx, [rcx+10h]
0x18003b459  call    WPP_SF_
0x18003b45e  mov     r8d, 4B2h
0x18003b464  jmp     loc_18003B4F1
0x18003b469  mov     r9d, dword ptr [rbp+var_18+8]
0x18003b46d  lea     ecx, [r9-2]
0x18003b471  test    ecx, 0FFFFFFF9h
0x18003b477  jnz     short loc_18003B483
0x18003b479  cmp     r9d, 6
0x18003b47d  jz      short loc_18003B483
0x18003b47f  mov     eax, ebx
0x18003b481  jmp     short loc_18003B501
0x18003b483  lea     rax, WPP_GLOBAL_Control
0x18003b48a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b491  cmp     rcx, rax
0x18003b494  jz      short loc_18003B4B0
0x18003b496  test    [rcx+1Ch], bl
0x18003b499  jz      short loc_18003B4B0
0x18003b49b  mov     edx, 33h ; '3'
0x18003b4a0  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003b4a7  mov     rcx, [rcx+10h]
0x18003b4ab  call    WPP_SF_d
0x18003b4b0  mov     r8d, 4C4h
0x18003b4b6  jmp     short loc_18003B4F1
0x18003b4b8  lea     rax, WPP_GLOBAL_Control
0x18003b4bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b4c6  cmp     rcx, rax
0x18003b4c9  jz      short loc_18003B4EB
0x18003b4cb  mov     ebx, 1
0x18003b4d0  test    [rcx+1Ch], bl
0x18003b4d3  jz      short loc_18003B4EB
0x18003b4d5  lea     edx, [rbx+2Ah]
0x18003b4d8  mov     r9d, [r9]
0x18003b4db  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003b4e2  mov     rcx, [rcx+10h]
0x18003b4e6  call    WPP_SF_d
0x18003b4eb  mov     r8d, 4B1h; unsigned __int16
0x18003b4f1  lea     rdx, aQmnotify; "qmnotify"
0x18003b4f8  xor     ecx, ecx; int
0x18003b4fa  call    ?LogMsgBOOL@@YAXHPEA_WG@Z; LogMsgBOOL(int,wchar_t *,ushort)
0x18003b4ff  xor     eax, eax
0x18003b501  mov     rbx, [rsp+70h+arg_8]
0x18003b509  add     rsp, 70h
0x18003b50d  pop     rdi
0x18003b50e  pop     rsi
0x18003b50f  pop     rbp
0x18003b510  retn
```
