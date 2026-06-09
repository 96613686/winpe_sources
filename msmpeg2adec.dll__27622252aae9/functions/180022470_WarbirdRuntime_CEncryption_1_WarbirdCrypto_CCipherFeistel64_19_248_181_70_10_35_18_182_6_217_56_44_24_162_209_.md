# WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2 *,int)

- ea: `0x180022470`
- end: `0x180022818`
- name: `?DoCrypt@?$CEncryption@$00V?$CCipherFeistel64@$0BD@$0PI@$0LF@$0EG@$09$0CD@$0BC@$0LG@$05$0NJ@$0DI@$0CM@$0BI@$0KC@$0NB@$0JF@$0BA@$0NF@$0NO@$0LH@$0BE@$0CD@$0DD@$0CI@$0BN@$0IL@$0HD@$0NF@$0M@$0OE@$0BK@$0PN@$03$0FI@$0HI@$0DF@$0BF@$0OF@$0CP@$0OD@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$0A@$0ENFLKLIPNEIOMFLN@@2@UENCRYPTED_SEGMENT_DATA_CONST_2@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_2@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_2@2@H@Z`
- size: `936`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001fe90`
- `0x180023e40`

## callees

- `0x1800017b0`
- `0x18001f500`
- `0x18001f800`
- `0x180022470`
- `0x180023a70`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022580`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002260a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800227cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022580`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002260a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800227cd`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180022566`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800225eb`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800227b3`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180022566`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800225eb`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800227b3`

## pseudocode

```c
__int64 __fastcall WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::DoCrypt(
        __int64 a1,
        __int64 a2,
        int a3)
{
  unsigned int v3; // edx
  int v5; // r15d
  unsigned int v6; // esi
  __int64 v7; // rcx
  struct HINSTANCE__ *v8; // r12
  __int64 v9; // rbx
  unsigned __int64 v10; // rdi
  HANDLE CurrentThread; // rax
  BOOL v12; // r14d
  HANDLE v13; // rax
  __int64 v14; // r14
  __int16 v15; // ax
  HANDLE v16; // rax
  _BYTE v18[4]; // [rsp+48h] [rbp-29h] BYREF
  int v19; // [rsp+4Ch] [rbp-25h] BYREF
  LPVOID lpAddress; // [rsp+50h] [rbp-21h]
  SIZE_T dwSize; // [rsp+58h] [rbp-19h]
  __int64 v22; // [rsp+60h] [rbp-11h]
  int v23; // [rsp+68h] [rbp-9h]
  __int64 v24; // [rsp+70h] [rbp-1h]
  DWORD flOldProtect[2]; // [rsp+78h] [rbp+7h] BYREF
  _BYTE v26[16]; // [rsp+80h] [rbp+Fh] BYREF
  char v27; // [rsp+90h] [rbp+1Fh]

  v3 = *(_DWORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_4;
  lpAddress = 0;
  v5 = 0;
  dwSize = 0;
  v6 = 0;
  v22 = 0;
  v23 = a3;
  v24 = 0;
  *(_QWORD *)flOldProtect = 0;
  if ( (*(_DWORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_4 & 0x1FFFE) != 0 )
  {
    do
    {
      if ( v5 < 0 )
        break;
      v7 = v6;
      v8 = (struct HINSTANCE__ *)((char *)&_ImageBase + v7 * 8 + 674052);
      v9 = qword_1800A48C8[v7 + 8] & 0xFFFFFFF;
      v10 = (unsigned __int64)&_ImageBase + (*(_DWORD *)v8 & 0xFFFFFFF);
      if ( v10 < (unsigned __int64)lpAddress || v9 + v10 >= (unsigned __int64)lpAddress + dwSize )
      {
        if ( flOldProtect[0] )
        {
          WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
            (WarbirdRuntime::AutoEnableDynamicCodeGen *)v26,
            v3);
          VirtualProtect(lpAddress, dwSize, flOldProtect[1] | 0x40000000, &flOldProtect[1]);
          flOldProtect[0] = 0;
          if ( v27 )
          {
            v19 = 0;
            CurrentThread = GetCurrentThread();
            ((void (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(
              CurrentThread,
              2,
              &v19,
              4);
          }
        }
        lpAddress = (LPVOID)(v10 & 0xFFFFFFFFFFFFF000uLL);
        dwSize = ((v10 + v9 + 4095) & 0xFFFFFFFFFFFFF000uLL) - (v10 & 0xFFFFFFFFFFFFF000uLL);
        WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
          (WarbirdRuntime::AutoEnableDynamicCodeGen *)v26,
          v3);
        v12 = VirtualProtect(lpAddress, dwSize, 0x40000040u, &flOldProtect[1]);
        flOldProtect[0] = v12;
        if ( v27 )
        {
          v19 = 0;
          v13 = GetCurrentThread();
          ((void (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(
            v13,
            2,
            &v19,
            4);
        }
        v3 = *(_DWORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_4;
        if ( !v12 )
          goto LABEL_17;
      }
      if ( v10 + v22 )
      {
        v14 = 2LL * v6;
        v15 = *(_WORD *)&algn_1800AD584[v14] & 0x10;
        if ( a3 )
        {
          if ( !v15 )
          {
            v18[0] = 0;
            WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Encrypt(
              v10,
              v10 + v22,
              v9,
              0,
              *(_DWORD *)v8 & 0xFFFFFFF,
              (__int64)v18);
            v3 = *(_DWORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_4;
            *(_WORD *)&algn_1800AD584[v14] &= 0xE01Fu;
            *(_WORD *)&algn_1800AD584[v14] |= (unsigned __int16)(32 * v18[0]) | 0x10;
          }
        }
        else if ( v15 )
        {
          WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Decrypt(
            v10,
            v10 + v22,
            v9,
            0,
            *(_DWORD *)v8 & 0xFFFFFFF,
            *(_WORD *)&algn_1800AD584[v14] >> 5,
            (*(_WORD *)&algn_1800AD584[v14] & 1) == 0);
          v3 = *(_DWORD *)&WarbirdRuntime::g_EncryptedSegmentConstData_4;
          *(_WORD *)&algn_1800AD584[v14] = *(_WORD *)&algn_1800AD584[v14] & 0xFFEE | 1;
        }
      }
      else
      {
LABEL_17:
        v5 = -2147024882;
      }
      ++v6;
    }
    while ( v6 < (unsigned __int16)(v3 >> 1) );
    if ( flOldProtect[0] )
    {
      WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
        (WarbirdRuntime::AutoEnableDynamicCodeGen *)v26,
        v3);
      VirtualProtect(lpAddress, dwSize, flOldProtect[1] | 0x40000000, &flOldProtect[1]);
      flOldProtect[0] = 0;
      if ( v27 )
      {
        v19 = 0;
        v16 = GetCurrentThread();
        ((void (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(
          v16,
          2,
          &v19,
          4);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180022470  mov     r11, rsp
0x180022473  push    rbp
0x180022474  push    rsi
0x180022475  push    r13
0x180022477  push    r14
0x180022479  push    r15
0x18002247b  lea     rbp, [r11-5Fh]
0x18002247f  sub     rsp, 0A0h
0x180022486  mov     rax, cs:__security_cookie
0x18002248d  xor     rax, rsp
0x180022490  mov     [rbp+57h+var_30], rax
0x180022494  mov     rdx, cs:?g_EncryptedSegmentConstData_4@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_2@1@A; bool
0x18002249b  xor     r14d, r14d
0x18002249e  movzx   eax, cs:byte_1800A48C0
0x1800224a5  mov     r13d, r8d
0x1800224a8  mov     [rbp+57h+lpAddress], r14
0x1800224ac  mov     r15d, r14d
0x1800224af  mov     [rbp+57h+dwSize], r14
0x1800224b3  mov     esi, r14d
0x1800224b6  mov     [rbp+57h+var_68], r14
0x1800224ba  mov     [rbp+57h+var_60], r8d
0x1800224be  mov     [rbp+57h+var_58], rax
0x1800224c2  mov     qword ptr [rbp+57h+flOldProtect], r14
0x1800224c6  test    edx, 1FFFEh
0x1800224cc  jbe     loc_1800227F8
0x1800224d2  mov     r9, cs:qword_1800A48B8
0x1800224d9  lea     r8, __ImageBase
0x1800224e0  mov     [r11+8], rbx
0x1800224e4  mov     [r11+10h], rdi
0x1800224e8  mov     [r11+18h], r12
0x1800224ec  nop     dword ptr [rax+00h]
0x1800224f0  test    r15d, r15d
0x1800224f3  js      loc_180022777
0x1800224f9  mov     eax, esi
0x1800224fb  lea     rcx, ds:0[rax*8]
0x180022503  mov     ebx, [rcx+r8+0A4908h]
0x18002250b  lea     r12, [rcx+0A4904h]
0x180022512  mov     rcx, [rbp+57h+lpAddress]
0x180022516  add     r12, r8
0x180022519  and     ebx, 0FFFFFFFh
0x18002251f  mov     edi, [r12]
0x180022523  and     edi, 0FFFFFFFh
0x180022529  add     rdi, r8
0x18002252c  cmp     rdi, rcx
0x18002252f  jb      short loc_180022542
0x180022531  add     rcx, [rbp+57h+dwSize]
0x180022535  lea     rax, [rbx+rdi]
0x180022539  cmp     rax, rcx
0x18002253c  jb      loc_180022653
0x180022542  cmp     [rbp+57h+flOldProtect], 0
0x180022546  jz      short loc_1800225AB
0x180022548  lea     rcx, [rbp+57h+var_48]; this
0x18002254c  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x180022551  mov     r8d, [rbp+57h+flOldProtect+4]
0x180022555  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x180022559  mov     rdx, [rbp+57h+dwSize]; dwSize
0x18002255d  bts     r8d, 1Eh; flNewProtect
0x180022562  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x180022566  call    cs:__imp_VirtualProtect
0x18002256d  nop     dword ptr [rax+rax+00h]
0x180022572  cmp     [rbp+57h+var_38], 0
0x180022576  mov     [rbp+57h+flOldProtect], r14d
0x18002257a  jz      short loc_1800225AB
0x18002257c  mov     [rbp+57h+var_7C], r14d
0x180022580  call    cs:__imp_GetCurrentThread
0x180022587  nop     dword ptr [rax+rax+00h]
0x18002258c  mov     r9d, 4
0x180022592  lea     r8, [rbp+57h+var_7C]
0x180022596  mov     rcx, rax
0x180022599  mov     edx, 2
0x18002259e  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x1800225a5  call    cs:__guard_dispatch_icall_fptr
0x1800225ab  lea     rax, [rbx+0FFFh]
0x1800225b2  mov     rcx, rdi
0x1800225b5  and     rcx, 0FFFFFFFFFFFFF000h
0x1800225bc  add     rax, rdi
0x1800225bf  and     rax, 0FFFFFFFFFFFFF000h
0x1800225c5  mov     [rbp+57h+lpAddress], rcx
0x1800225c9  sub     rax, rcx
0x1800225cc  lea     rcx, [rbp+57h+var_48]; this
0x1800225d0  mov     [rbp+57h+dwSize], rax
0x1800225d4  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x1800225d9  mov     rdx, [rbp+57h+dwSize]; dwSize
0x1800225dd  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x1800225e1  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x1800225e5  mov     r8d, 40000040h; flNewProtect
0x1800225eb  call    cs:__imp_VirtualProtect
0x1800225f2  nop     dword ptr [rax+rax+00h]
0x1800225f7  cmp     [rbp+57h+var_38], 0
0x1800225fb  mov     r14d, eax
0x1800225fe  mov     [rbp+57h+flOldProtect], eax
0x180022601  jz      short loc_180022635
0x180022603  mov     [rbp+57h+var_7C], 0
0x18002260a  call    cs:__imp_GetCurrentThread
0x180022611  nop     dword ptr [rax+rax+00h]
0x180022616  mov     r9d, 4
0x18002261c  lea     r8, [rbp+57h+var_7C]
0x180022620  mov     rcx, rax
0x180022623  mov     edx, 2
0x180022628  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x18002262f  call    cs:__guard_dispatch_icall_fptr
0x180022635  mov     r9, cs:qword_1800A48B8
0x18002263c  mov     rdx, cs:?g_EncryptedSegmentConstData_4@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_2@1@A; bool
0x180022643  test    r14d, r14d
0x180022646  jz      loc_180022753
0x18002264c  lea     r8, __ImageBase
0x180022653  mov     r10, [rbp+57h+var_68]
0x180022657  add     r10, rdi
0x18002265a  jz      loc_180022753
0x180022660  mov     eax, esi
0x180022662  lea     r14, [rax+rax]
0x180022666  movzx   r8d, word ptr [r14+r8+0AD584h]
0x18002266f  movzx   eax, r8w
0x180022673  and     ax, 10h
0x180022677  test    r13d, r13d
0x18002267a  jz      short loc_1800226E6
0x18002267c  test    ax, ax
0x18002267f  jnz     loc_180022759
0x180022685  mov     [rbp+57h+var_80], al
0x180022688  lea     rcx, [rbp+57h+var_80]
0x18002268c  mov     eax, [r12]
0x180022690  mov     r8, rbx
0x180022693  mov     qword ptr [rsp+0C0h+var_98], rcx
0x180022698  and     eax, 0FFFFFFFh
0x18002269d  mov     rdx, r10
0x1800226a0  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800226a4  mov     rcx, rdi
0x1800226a7  call    ?Encrypt@?$CEncryption@$00V?$CCipherFeistel64@$0BD@$0PI@$0LF@$0EG@$09$0CD@$0BC@$0LG@$05$0NJ@$0DI@$0CM@$0BI@$0KC@$0NB@$0JF@$0BA@$0NF@$0NO@$0LH@$0BE@$0CD@$0DD@$0CI@$0BN@$0IL@$0HD@$0NF@$0M@$0OE@$0BK@$0PN@$03$0FI@$0HI@$0DF@$0BF@$0OF@$0CP@$0OD@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$0A@$0ENFLKLIPNEIOMFLN@@2@UENCRYPTED_SEGMENT_DATA_CONST_2@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@K1@Z; WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Encrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar *)
0x1800226ac  mov     r9, cs:qword_1800A48B8
0x1800226b3  lea     r8, __ImageBase
0x1800226ba  mov     rdx, cs:?g_EncryptedSegmentConstData_4@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_2@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2 WarbirdRuntime::g_EncryptedSegmentConstData_4
0x1800226c1  mov     eax, 0E01Fh
0x1800226c6  and     [r14+r8+0AD584h], ax
0x1800226cf  movzx   eax, [rbp+57h+var_80]
0x1800226d3  shl     ax, 5
0x1800226d7  or      ax, 10h
0x1800226db  or      [r14+r8+0AD584h], ax
0x1800226e4  jmp     short loc_180022760
0x1800226e6  test    ax, ax
0x1800226e9  jz      short loc_180022759
0x1800226eb  mov     eax, [r12]
0x1800226ef  movzx   ecx, r8w
0x1800226f3  not     cx
0x1800226f6  shr     r8w, 5
0x1800226fb  and     ecx, 1
0x1800226fe  and     eax, 0FFFFFFFh
0x180022703  mov     dword ptr [rsp+0C0h+var_90], ecx
0x180022707  mov     rdx, r10
0x18002270a  mov     byte ptr [rsp+0C0h+var_98], r8b
0x18002270f  mov     rcx, rdi
0x180022712  mov     r8, rbx
0x180022715  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180022719  call    ?Decrypt@?$CEncryption@$00V?$CCipherFeistel64@$0BD@$0PI@$0LF@$0EG@$09$0CD@$0BC@$0LG@$05$0NJ@$0DI@$0CM@$0BI@$0KC@$0NB@$0JF@$0BA@$0NF@$0NO@$0LH@$0BE@$0CD@$0DD@$0CI@$0BN@$0IL@$0HD@$0NF@$0M@$0OE@$0BK@$0PN@$03$0FI@$0HI@$0DF@$0BF@$0OF@$0CP@$0OD@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$0A@$0ENFLKLIPNEIOMFLN@@2@UENCRYPTED_SEGMENT_DATA_CONST_2@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@KEH@Z; WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Decrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar,int)
0x18002271e  mov     r9, cs:qword_1800A48B8
0x180022725  lea     r8, __ImageBase
0x18002272c  movzx   eax, word ptr [r14+r8+0AD584h]
0x180022735  mov     ecx, 0FFEFh
0x18002273a  mov     rdx, cs:?g_EncryptedSegmentConstData_4@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_2@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2 WarbirdRuntime::g_EncryptedSegmentConstData_4
0x180022741  and     ax, cx
0x180022744  or      ax, 1
0x180022748  mov     [r14+r8+0AD584h], ax
0x180022751  jmp     short loc_180022760
0x180022753  mov     r15d, 8007000Eh
0x180022759  lea     r8, __ImageBase
0x180022760  mov     eax, edx
0x180022762  inc     esi
0x180022764  shr     eax, 1
0x180022766  mov     r14d, 0
0x18002276c  movzx   eax, ax
0x18002276f  cmp     esi, eax
0x180022771  jb      loc_1800224F0
0x180022777  cmp     [rbp+57h+flOldProtect], 0
0x18002277b  mov     r12, [rsp+0C0h+arg_10]
0x180022783  mov     rdi, [rsp+0C0h+arg_8]
0x18002278b  mov     rbx, [rsp+0C0h+arg_0]
0x180022793  jz      short loc_1800227F8
0x180022795  lea     rcx, [rbp+57h+var_48]; this
0x180022799  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x18002279e  mov     r8d, [rbp+57h+flOldProtect+4]
0x1800227a2  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x1800227a6  mov     rdx, [rbp+57h+dwSize]; dwSize
0x1800227aa  bts     r8d, 1Eh; flNewProtect
0x1800227af  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x1800227b3  call    cs:__imp_VirtualProtect
0x1800227ba  nop     dword ptr [rax+rax+00h]
0x1800227bf  cmp     [rbp+57h+var_38], 0
0x1800227c3  mov     [rbp+57h+flOldProtect], r14d
0x1800227c7  jz      short loc_1800227F8
0x1800227c9  mov     [rbp+57h+var_7C], r14d
0x1800227cd  call    cs:__imp_GetCurrentThread
0x1800227d4  nop     dword ptr [rax+rax+00h]
0x1800227d9  mov     r9d, 4
0x1800227df  lea     r8, [rbp+57h+var_7C]
0x1800227e3  mov     rcx, rax
0x1800227e6  mov     edx, 2
0x1800227eb  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x1800227f2  call    cs:__guard_dispatch_icall_fptr
0x1800227f8  mov     eax, r15d
0x1800227fb  mov     rcx, [rbp+57h+var_30]
0x1800227ff  xor     rcx, rsp; StackCookie
0x180022802  call    __security_check_cookie
0x180022807  add     rsp, 0A0h
0x18002280e  pop     r15
0x180022810  pop     r14
0x180022812  pop     r13
0x180022814  pop     rsi
0x180022815  pop     rbp
0x180022816  retn
```
