# WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7 *,int)

- ea: `0x1800232d0`
- end: `0x180023695`
- name: `?DoCrypt@?$CEncryption@$05V?$CCipherFeistel64@$07$0JI@$0KN@$0HJ@$0P@$0FC@$0EG@$0LP@$0L@$0GK@$0CN@$0JI@$02$0DN@$0ED@$08$0M@$0HL@$0DN@$0GO@$04$0KF@$0PE@$0CJ@$0BM@$0NK@$0CA@$0HN@$0A@$0O@$0EG@$0EI@$0BC@$0JE@$0PJ@$0CA@$08$0IG@$0FF@$0ED@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$01$02$0FLGHJNDFFJOLLCJB@@2@UENCRYPTED_SEGMENT_DATA_CONST_7@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_7@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_7@2@H@Z`
- size: `965`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180021a20`
- `0x180024b70`

## callees

- `0x1800017b0`
- `0x18001f500`
- `0x1800213a0`
- `0x1800232d0`
- `0x180024790`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800233f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002347d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002364a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800233f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002347d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002364a`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800233d9`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18002345e`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180023630`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800233d9`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18002345e`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180023630`

## pseudocode

```c
__int64 __fastcall WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::DoCrypt(
        __int64 a1,
        int a2,
        int a3)
{
  unsigned int v4; // r8d
  int v5; // r15d
  unsigned int v6; // esi
  __int64 v7; // rbx
  struct HINSTANCE__ *v8; // r12
  __int64 v9; // rbx
  unsigned __int64 v10; // rdi
  HANDLE CurrentThread; // rax
  BOOL v12; // r14d
  HANDLE v13; // rax
  __int64 v14; // r14
  unsigned __int16 v15; // r10
  __int16 v16; // ax
  unsigned int v17; // ecx
  HANDLE v18; // rax
  char v20[4]; // [rsp+40h] [rbp-29h] BYREF
  int v21; // [rsp+44h] [rbp-25h] BYREF
  LPVOID lpAddress; // [rsp+48h] [rbp-21h]
  SIZE_T dwSize; // [rsp+50h] [rbp-19h]
  __int64 v24; // [rsp+58h] [rbp-11h]
  int v25; // [rsp+60h] [rbp-9h]
  __int64 v26; // [rsp+68h] [rbp-1h]
  DWORD flOldProtect[2]; // [rsp+70h] [rbp+7h] BYREF
  _BYTE v28[16]; // [rsp+78h] [rbp+Fh] BYREF
  char v29; // [rsp+88h] [rbp+1Fh]

  v25 = a3;
  v4 = WarbirdRuntime::g_EncryptedSegmentConstData_66;
  v5 = 0;
  lpAddress = 0;
  v6 = 0;
  dwSize = 0;
  v24 = 0;
  v26 = 0;
  *(_QWORD *)flOldProtect = 0;
  if ( (WarbirdRuntime::g_EncryptedSegmentConstData_66 & 0x1FFFE) != 0 )
  {
    do
    {
      if ( v5 < 0 )
        break;
      v7 = v6;
      v8 = (struct HINSTANCE__ *)((char *)&_ImageBase + v7 * 8 + 674336);
      v9 = HIDWORD(qword_1800A4A20[v7]) & 0xFFFFFFF;
      v10 = (unsigned __int64)&_ImageBase + ((*(_DWORD *)v8 >> 1) & 0xFFFFFFF);
      if ( v10 < (unsigned __int64)lpAddress
        || (LOBYTE(a2) = v9 + v10, v9 + v10 >= (unsigned __int64)lpAddress + dwSize) )
      {
        if ( flOldProtect[0] )
        {
          WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
            (WarbirdRuntime::AutoEnableDynamicCodeGen *)v28,
            a2);
          VirtualProtect(lpAddress, dwSize, flOldProtect[1] | 0x40000000, &flOldProtect[1]);
          flOldProtect[0] = 0;
          if ( v29 )
          {
            v21 = 0;
            CurrentThread = GetCurrentThread();
            ((void (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(
              CurrentThread,
              2,
              &v21,
              4);
          }
        }
        lpAddress = (LPVOID)(v10 & 0xFFFFFFFFFFFFF000uLL);
        dwSize = ((v9 + v10 + 4095) & 0xFFFFFFFFFFFFF000uLL) - (v10 & 0xFFFFFFFFFFFFF000uLL);
        WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
          (WarbirdRuntime::AutoEnableDynamicCodeGen *)v28,
          a2);
        v12 = VirtualProtect(lpAddress, dwSize, 0x40000040u, &flOldProtect[1]);
        flOldProtect[0] = v12;
        if ( v29 )
        {
          v21 = 0;
          v13 = GetCurrentThread();
          ((void (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(
            v13,
            2,
            &v21,
            4);
        }
        v4 = WarbirdRuntime::g_EncryptedSegmentConstData_66;
        if ( !v12 )
          goto LABEL_17;
      }
      a2 = v10 + v24;
      if ( v10 + v24 )
      {
        v14 = 2LL * v6;
        v15 = *(_WORD *)&algn_1800AD59C[v14];
        v16 = v15 & 0x800;
        if ( a3 )
        {
          if ( !v16 )
          {
            v20[0] = 0;
            WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Encrypt(
              v10,
              a2,
              v9,
              0,
              (*(_DWORD *)v8 >> 1) & 0xFFFFFFF,
              (__int64)v20);
            v4 = WarbirdRuntime::g_EncryptedSegmentConstData_66;
            algn_1800AD59C[v14] = v20[0];
            *(_WORD *)&algn_1800AD59C[v14] |= 0x800u;
          }
        }
        else if ( v16 )
        {
          v17 = v15;
          LOWORD(v17) = ~v15;
          WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Decrypt(
            v10,
            a2,
            v9,
            0,
            (*(_DWORD *)v8 >> 1) & 0xFFFFFFF,
            v15,
            (v17 >> 8) & 1);
          v4 = WarbirdRuntime::g_EncryptedSegmentConstData_66;
          *(_WORD *)&algn_1800AD59C[v14] = *(_WORD *)&algn_1800AD59C[v14] & 0xF6FF | 0x100;
        }
      }
      else
      {
LABEL_17:
        v5 = -2147024882;
      }
      ++v6;
    }
    while ( v6 < (unsigned __int16)(v4 >> 1) );
    if ( flOldProtect[0] )
    {
      WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
        (WarbirdRuntime::AutoEnableDynamicCodeGen *)v28,
        a2);
      VirtualProtect(lpAddress, dwSize, flOldProtect[1] | 0x40000000, &flOldProtect[1]);
      flOldProtect[0] = 0;
      if ( v29 )
      {
        v21 = 0;
        v18 = GetCurrentThread();
        ((void (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(
          v18,
          2,
          &v21,
          4);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800232d0  push    rbp
0x1800232d2  push    rsi
0x1800232d3  push    r13
0x1800232d5  push    r14
0x1800232d7  push    r15
0x1800232d9  lea     rbp, [rsp-37h]
0x1800232de  sub     rsp, 0A0h
0x1800232e5  mov     rax, cs:__security_cookie
0x1800232ec  xor     rax, rsp
0x1800232ef  mov     [rbp+57h+var_30], rax
0x1800232f3  movzx   eax, cs:byte_1800A4A14
0x1800232fa  xor     r14d, r14d
0x1800232fd  mov     r13d, r8d
0x180023300  mov     [rbp+57h+var_60], r8d
0x180023304  mov     r8, cs:?g_EncryptedSegmentConstData_66@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_7@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7 WarbirdRuntime::g_EncryptedSegmentConstData_66
0x18002330b  mov     r15d, r14d
0x18002330e  mov     [rbp+57h+lpAddress], r14
0x180023312  mov     esi, r14d
0x180023315  mov     [rbp+57h+dwSize], r14
0x180023319  mov     [rbp+57h+var_68], r14
0x18002331d  mov     [rbp+57h+var_58], rax
0x180023321  mov     qword ptr [rbp+57h+flOldProtect], r14
0x180023325  test    r8d, 1FFFEh
0x18002332c  jbe     loc_180023675
0x180023332  mov     r9, cs:qword_1800A4A18
0x180023339  lea     r10, __ImageBase
0x180023340  mov     [rsp+0C0h+arg_0], rbx
0x180023348  mov     r11d, 800h
0x18002334e  mov     [rsp+0C0h+arg_8], rdi
0x180023356  mov     [rsp+0C0h+arg_10], r12
0x18002335e  xchg    ax, ax
0x180023360  test    r15d, r15d
0x180023363  js      loc_1800235F4
0x180023369  mov     rcx, [rbp+57h+lpAddress]
0x18002336d  mov     eax, esi
0x18002336f  lea     rbx, ds:0[rax*8]
0x180023377  lea     r12, [rbx+0A4A20h]
0x18002337e  mov     ebx, [rbx+r10+0A4A24h]
0x180023386  add     r12, r10
0x180023389  and     ebx, 0FFFFFFFh
0x18002338f  mov     edi, [r12]
0x180023393  shr     rdi, 1
0x180023396  and     edi, 0FFFFFFFh
0x18002339c  add     rdi, r10
0x18002339f  cmp     rdi, rcx
0x1800233a2  jb      short loc_1800233B5
0x1800233a4  add     rcx, [rbp+57h+dwSize]
0x1800233a8  lea     rdx, [rbx+rdi]; bool
0x1800233ac  cmp     rdx, rcx
0x1800233af  jb      loc_1800234CC
0x1800233b5  cmp     [rbp+57h+flOldProtect], 0
0x1800233b9  jz      short loc_18002341E
0x1800233bb  lea     rcx, [rbp+57h+var_48]; this
0x1800233bf  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x1800233c4  mov     r8d, [rbp+57h+flOldProtect+4]
0x1800233c8  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x1800233cc  mov     rdx, [rbp+57h+dwSize]; dwSize
0x1800233d0  bts     r8d, 1Eh; flNewProtect
0x1800233d5  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x1800233d9  call    cs:__imp_VirtualProtect
0x1800233e0  nop     dword ptr [rax+rax+00h]
0x1800233e5  cmp     [rbp+57h+var_38], 0
0x1800233e9  mov     [rbp+57h+flOldProtect], r14d
0x1800233ed  jz      short loc_18002341E
0x1800233ef  mov     [rbp+57h+var_7C], r14d
0x1800233f3  call    cs:__imp_GetCurrentThread
0x1800233fa  nop     dword ptr [rax+rax+00h]
0x1800233ff  mov     r9d, 4
0x180023405  lea     r8, [rbp+57h+var_7C]
0x180023409  mov     rcx, rax
0x18002340c  mov     edx, 2
0x180023411  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x180023418  call    cs:__guard_dispatch_icall_fptr
0x18002341e  lea     rax, [rdi+0FFFh]
0x180023425  mov     rcx, rdi
0x180023428  and     rcx, 0FFFFFFFFFFFFF000h
0x18002342f  add     rax, rbx
0x180023432  and     rax, 0FFFFFFFFFFFFF000h
0x180023438  mov     [rbp+57h+lpAddress], rcx
0x18002343c  sub     rax, rcx
0x18002343f  lea     rcx, [rbp+57h+var_48]; this
0x180023443  mov     [rbp+57h+dwSize], rax
0x180023447  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x18002344c  mov     rdx, [rbp+57h+dwSize]; dwSize
0x180023450  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x180023454  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x180023458  mov     r8d, 40000040h; flNewProtect
0x18002345e  call    cs:__imp_VirtualProtect
0x180023465  nop     dword ptr [rax+rax+00h]
0x18002346a  cmp     [rbp+57h+var_38], 0
0x18002346e  mov     r14d, eax
0x180023471  mov     [rbp+57h+flOldProtect], eax
0x180023474  jz      short loc_1800234A8
0x180023476  mov     [rbp+57h+var_7C], 0
0x18002347d  call    cs:__imp_GetCurrentThread
0x180023484  nop     dword ptr [rax+rax+00h]
0x180023489  mov     r9d, 4
0x18002348f  lea     r8, [rbp+57h+var_7C]
0x180023493  mov     rcx, rax
0x180023496  mov     edx, 2
0x18002349b  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x1800234a2  call    cs:__guard_dispatch_icall_fptr
0x1800234a8  mov     r9, cs:qword_1800A4A18
0x1800234af  mov     r8, cs:?g_EncryptedSegmentConstData_66@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_7@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7 WarbirdRuntime::g_EncryptedSegmentConstData_66
0x1800234b6  test    r14d, r14d
0x1800234b9  jz      loc_1800235C9
0x1800234bf  lea     r10, __ImageBase
0x1800234c6  mov     r11d, 800h
0x1800234cc  mov     rdx, [rbp+57h+var_68]
0x1800234d0  add     rdx, rdi
0x1800234d3  jz      loc_1800235C9
0x1800234d9  mov     eax, esi
0x1800234db  lea     r14, [rax+rax]
0x1800234df  movzx   r10d, word ptr [r14+r10+0AD59Ch]
0x1800234e8  movzx   eax, r10w
0x1800234ec  and     ax, r11w
0x1800234f0  test    r13d, r13d
0x1800234f3  jz      short loc_180023559
0x1800234f5  test    ax, ax
0x1800234f8  jnz     loc_1800235D5
0x1800234fe  mov     [rbp+57h+var_80], al
0x180023501  lea     rcx, [rbp+57h+var_80]
0x180023505  mov     eax, [r12]
0x180023509  mov     r8, rbx
0x18002350c  mov     [rsp+0C0h+var_98], rcx
0x180023511  mov     rcx, rdi
0x180023514  shr     eax, 1
0x180023516  and     eax, 0FFFFFFFh
0x18002351b  mov     [rsp+0C0h+var_A0], eax
0x18002351f  call    ?Encrypt@?$CEncryption@$05V?$CCipherFeistel64@$07$0JI@$0KN@$0HJ@$0P@$0FC@$0EG@$0LP@$0L@$0GK@$0CN@$0JI@$02$0DN@$0ED@$08$0M@$0HL@$0DN@$0GO@$04$0KF@$0PE@$0CJ@$0BM@$0NK@$0CA@$0HN@$0A@$0O@$0EG@$0EI@$0BC@$0JE@$0PJ@$0CA@$08$0IG@$0FF@$0ED@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$01$02$0FLGHJNDFFJOLLCJB@@2@UENCRYPTED_SEGMENT_DATA_CONST_7@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@K1@Z; WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Encrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar *)
0x180023524  movzx   eax, [rbp+57h+var_80]
0x180023528  lea     r10, __ImageBase
0x18002352f  mov     r9, cs:qword_1800A4A18
0x180023536  mov     r11d, 800h
0x18002353c  mov     r8, cs:?g_EncryptedSegmentConstData_66@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_7@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7 WarbirdRuntime::g_EncryptedSegmentConstData_66
0x180023543  mov     [r14+r10+0AD59Ch], al
0x18002354b  or      [r14+r10+0AD59Ch], r11w
0x180023554  jmp     loc_1800235DC
0x180023559  test    ax, ax
0x18002355c  jz      short loc_1800235D5
0x18002355e  mov     eax, [r12]
0x180023562  movzx   ecx, r10w
0x180023566  not     cx
0x180023569  shr     eax, 1
0x18002356b  shr     ecx, 8
0x18002356e  and     eax, 0FFFFFFFh
0x180023573  and     ecx, 1
0x180023576  mov     r8, rbx
0x180023579  mov     [rsp+0C0h+var_90], ecx
0x18002357d  mov     rcx, rdi
0x180023580  mov     byte ptr [rsp+0C0h+var_98], r10b
0x180023585  mov     [rsp+0C0h+var_A0], eax
0x180023589  call    ?Decrypt@?$CEncryption@$05V?$CCipherFeistel64@$07$0JI@$0KN@$0HJ@$0P@$0FC@$0EG@$0LP@$0L@$0GK@$0CN@$0JI@$02$0DN@$0ED@$08$0M@$0HL@$0DN@$0GO@$04$0KF@$0PE@$0CJ@$0BM@$0NK@$0CA@$0HN@$0A@$0O@$0EG@$0EI@$0BC@$0JE@$0PJ@$0CA@$08$0IG@$0FF@$0ED@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$01$02$0FLGHJNDFFJOLLCJB@@2@UENCRYPTED_SEGMENT_DATA_CONST_7@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@KEH@Z; WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Decrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar,int)
0x18002358e  mov     r9, cs:qword_1800A4A18
0x180023595  lea     r10, __ImageBase
0x18002359c  movzx   eax, word ptr [r14+r10+0AD59Ch]
0x1800235a5  mov     ecx, 0F7FFh
0x1800235aa  mov     r8, cs:?g_EncryptedSegmentConstData_66@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_7@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7 WarbirdRuntime::g_EncryptedSegmentConstData_66
0x1800235b1  and     ax, cx
0x1800235b4  or      ax, 100h
0x1800235b8  mov     r11d, 800h
0x1800235be  mov     [r14+r10+0AD59Ch], ax
0x1800235c7  jmp     short loc_1800235DC
0x1800235c9  mov     r15d, 8007000Eh
0x1800235cf  mov     r11d, 800h
0x1800235d5  lea     r10, __ImageBase
0x1800235dc  mov     eax, r8d
0x1800235df  inc     esi
0x1800235e1  shr     eax, 1
0x1800235e3  mov     r14d, 0
0x1800235e9  movzx   eax, ax
0x1800235ec  cmp     esi, eax
0x1800235ee  jb      loc_180023360
0x1800235f4  cmp     [rbp+57h+flOldProtect], 0
0x1800235f8  mov     r12, [rsp+0C0h+arg_10]
0x180023600  mov     rdi, [rsp+0C0h+arg_8]
0x180023608  mov     rbx, [rsp+0C0h+arg_0]
0x180023610  jz      short loc_180023675
0x180023612  lea     rcx, [rbp+57h+var_48]; this
0x180023616  call    ??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)
0x18002361b  mov     r8d, [rbp+57h+flOldProtect+4]
0x18002361f  lea     r9, [rbp+57h+flOldProtect+4]; lpflOldProtect
0x180023623  mov     rdx, [rbp+57h+dwSize]; dwSize
0x180023627  bts     r8d, 1Eh; flNewProtect
0x18002362c  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x180023630  call    cs:__imp_VirtualProtect
0x180023637  nop     dword ptr [rax+rax+00h]
0x18002363c  cmp     [rbp+57h+var_38], 0
0x180023640  mov     [rbp+57h+flOldProtect], r14d
0x180023644  jz      short loc_180023675
0x180023646  mov     [rbp+57h+var_7C], r14d
0x18002364a  call    cs:__imp_GetCurrentThread
0x180023651  nop     dword ptr [rax+rax+00h]
0x180023656  mov     r9d, 4
0x18002365c  lea     r8, [rbp+57h+var_7C]
0x180023660  mov     rcx, rax
0x180023663  mov     edx, 2
0x180023668  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x18002366f  call    cs:__guard_dispatch_icall_fptr
0x180023675  mov     eax, r15d
0x180023678  mov     rcx, [rbp+57h+var_30]
0x18002367c  xor     rcx, rsp; StackCookie
0x18002367f  call    __security_check_cookie
0x180023684  add     rsp, 0A0h
0x18002368b  pop     r15
0x18002368d  pop     r14
0x18002368f  pop     r13
0x180023691  pop     rsi
0x180023692  pop     rbp
0x180023693  retn
```
