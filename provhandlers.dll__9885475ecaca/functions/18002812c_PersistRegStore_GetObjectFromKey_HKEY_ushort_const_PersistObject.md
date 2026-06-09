# PersistRegStore::GetObjectFromKey(HKEY__ *,ushort const *,PersistObject * *)

- ea: `0x18002812c`
- end: `0x1800283f5`
- name: `?GetObjectFromKey@PersistRegStore@@IEAAJPEAUHKEY__@@PEBGPEAPEAVPersistObject@@@Z`
- size: `713`
- prototype: `__int64 __fastcall(PersistRegStore *this, HKEY, const unsigned __int16 *, struct PersistObject **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800274b0`

## callees

- `0x180002558`
- `0x180026b88`
- `0x18002812c`
- `0x180028498`
- `0x18002a864`
- `0x18002a978`
- `0x18002aab0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800282a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800282a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800282c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800282c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800281ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800281ba`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180028315`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180028315`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800283b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800283bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800283b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800283bd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800281fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002821a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800281fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002821a`
- `DMCmnUtils!SafeStringToDword` at `0x180028332`
- `DMCmnUtils!SafeStringToDword` at `0x180028332`
- `DMCmnUtils!CopyString` at `0x1800282b5`
- `DMCmnUtils!CopyString` at `0x1800282b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PersistRegStore::GetObjectFromKey(
        PersistRegStore *this,
        HKEY a2,
        const unsigned __int16 *a3,
        struct PersistObject **a4)
{
  WCHAR *v6; // r15
  BYTE *v7; // r14
  LSTATUS v8; // eax
  signed int v9; // edi
  _QWORD *v10; // rax
  _QWORD *v11; // rsi
  int v12; // eax
  DWORD v13; // ebx
  HKEY v14; // r12
  LSTATUS v15; // eax
  int v16; // eax
  unsigned int v18; // [rsp+68h] [rbp-9h] BYREF
  SIZE_T uBytes; // [rsp+6Ch] [rbp-5h] BYREF
  DWORD cValues; // [rsp+74h] [rbp+3h] BYREF
  DWORD cSubKeys; // [rsp+78h] [rbp+7h] BYREF
  DWORD cchValueName; // [rsp+7Ch] [rbp+Bh] BYREF
  DWORD Type; // [rsp+80h] [rbp+Fh] BYREF
  _QWORD *v24; // [rsp+88h] [rbp+17h]
  char v25; // [rsp+90h] [rbp+1Fh]
  DWORD cbMaxValueNameLen; // [rsp+D8h] [rbp+67h] BYREF
  int v27; // [rsp+DCh] [rbp+6Bh]
  HKEY hKey; // [rsp+E0h] [rbp+6Fh]

  hKey = a2;
  v27 = HIDWORD(this);
  cSubKeys = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  uBytes = 0;
  Type = 0;
  v18 = 0;
  v6 = 0;
  v7 = 0;
  v8 = RegQueryInfoKeyW(a2, 0, 0, 0, &cSubKeys, 0, 0, &cValues, &cbMaxValueNameLen, (LPDWORD)&uBytes, 0, 0);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
  }
  else if ( cSubKeys )
  {
    v9 = -2147418113;
  }
  else
  {
    v6 = (WCHAR *)LocalAlloc(0x40u, 2LL * ++cbMaxValueNameLen);
    if ( v6 )
    {
      v7 = (BYTE *)LocalAlloc(0x40u, (unsigned int)uBytes);
      if ( v7 )
      {
        v10 = operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
        v11 = v10;
        v24 = v10;
        if ( v10 )
        {
          *v10 = &PersistObject::`vftable';
          v10[1] = 0;
          v10[2] = 0;
          v10[3] = 0;
          *((_OWORD *)v10 + 2) = 0;
          *((_OWORD *)v10 + 3) = 0;
          v10[8] = 0;
          v12 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v10 + 4));
          if ( v12 < 0 )
            ATL::AtlThrowImpl(v12);
          v11[9] = 0;
          v11[10] = 0;
          v11[11] = 0;
        }
        else
        {
          v11 = 0;
        }
        if ( v11 )
        {
          v24 = v11 + 4;
          EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 4));
          v25 = 1;
          v9 = CopyString(a3, 0xFFFFFFFF, (unsigned __int16 **)v11 + 3);
          LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 4));
          if ( v9 >= 0 )
          {
            v13 = 0;
            if ( !cValues )
            {
LABEL_27:
              *a4 = (struct PersistObject *)v11;
              goto LABEL_30;
            }
            v14 = hKey;
            while ( 1 )
            {
              cchValueName = cbMaxValueNameLen;
              HIDWORD(uBytes) = uBytes;
              v15 = RegEnumValueW(v14, v13, v6, &cchValueName, 0, &Type, v7, (LPDWORD)&uBytes + 1);
              v9 = v15;
              if ( v15 )
                break;
              v9 = SafeStringToDword(v6, 10, 0, &v18);
              if ( v9 < 0 )
                goto LABEL_29;
              switch ( Type )
              {
                case 1u:
                  v16 = PersistObject::Set(v11, v18, v7);
                  break;
                case 3u:
                  v16 = PersistObject::Set(v11, v18, v7, HIDWORD(uBytes));
                  break;
                case 4u:
                  v16 = PersistObject::Set(v11, v18, *(unsigned int *)v7);
                  break;
                default:
                  v9 = -2147418113;
                  goto LABEL_29;
              }
              v9 = v16;
              if ( v16 < 0 )
                goto LABEL_29;
              if ( ++v13 >= cValues )
                goto LABEL_27;
            }
            if ( v15 > 0 )
              v9 = (unsigned __int16)v15 | 0x80070000;
          }
LABEL_29:
          (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
          goto LABEL_30;
        }
      }
    }
    v9 = -2147024882;
  }
LABEL_30:
  LocalFree(v6);
  LocalFree(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002812c  mov     r11, rsp
0x18002812f  mov     [r11+18h], rbx
0x180028133  mov     [r11+10h], rdx
0x180028137  mov     [r11+8], rcx
0x18002813b  push    rbp
0x18002813c  push    rsi
0x18002813d  push    rdi
0x18002813e  push    r12
0x180028140  push    r13
0x180028142  push    r14
0x180028144  push    r15
0x180028146  lea     rbp, [r11-5Fh]
0x18002814a  sub     rsp, 90h
0x180028151  mov     r13, r9
0x180028154  mov     r12, r8
0x180028157  mov     rax, rdx
0x18002815a  xor     ebx, ebx
0x18002815c  mov     [rbp+57h+cSubKeys], ebx
0x18002815f  mov     [rbp+57h+cValues], ebx
0x180028162  mov     [rbp+57h+cbMaxValueNameLen], ebx
0x180028165  mov     [rbp+57h+cchValueName], ebx
0x180028168  mov     dword ptr [rbp+57h+uBytes], ebx
0x18002816b  mov     dword ptr [rbp+57h+uBytes+4], ebx
0x18002816e  mov     [rbp+57h+Type], ebx
0x180028171  mov     [rbp+57h+var_60], ebx
0x180028174  mov     r15d, ebx
0x180028177  mov     r14d, ebx
0x18002817a  mov     [r11-70h], rbx
0x18002817e  mov     [r11-78h], rbx
0x180028182  lea     rcx, [rbp+57h+uBytes]
0x180028186  mov     [r11-80h], rcx
0x18002818a  lea     rcx, [rbp+57h+cbMaxValueNameLen]
0x18002818e  mov     [rsp+40h], rcx; lpcbMaxValueNameLen
0x180028193  lea     rcx, [rbp+57h+cValues]
0x180028197  mov     [rsp+0C0h+lpcValues], rcx; lpcValues
0x18002819c  mov     [rsp+0C0h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x1800281a1  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x1800281a6  lea     rcx, [rbp+57h+cSubKeys]
0x1800281aa  mov     [rsp+0C0h+lpcSubKeys], rcx; lpcSubKeys
0x1800281af  xor     r9d, r9d; lpReserved
0x1800281b2  xor     r8d, r8d; lpcchClass
0x1800281b5  xor     edx, edx; lpClass
0x1800281b7  mov     rcx, rax; hKey
0x1800281ba  call    cs:__imp_RegQueryInfoKeyW
0x1800281c0  mov     edi, eax
0x1800281c2  test    eax, eax
0x1800281c4  jz      short loc_1800281DA
0x1800281c6  jle     loc_1800283B1
0x1800281cc  movzx   edi, ax
0x1800281cf  or      edi, 80070000h
0x1800281d5  jmp     loc_1800283B1
0x1800281da  cmp     [rbp+57h+cSubKeys], ebx
0x1800281dd  jz      short loc_1800281E9
0x1800281df  mov     edi, 8000FFFFh
0x1800281e4  jmp     loc_1800283B1
0x1800281e9  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1800281ec  inc     eax
0x1800281ee  mov     [rbp+57h+cbMaxValueNameLen], eax
0x1800281f1  mov     edx, eax
0x1800281f3  add     rdx, rdx; uBytes
0x1800281f6  mov     edi, 40h ; '@'
0x1800281fb  mov     ecx, edi; uFlags
0x1800281fd  call    cs:__imp_LocalAlloc
0x180028203  mov     r15, rax
0x180028206  test    rax, rax
0x180028209  jnz     short loc_180028215
0x18002820b  mov     edi, 8007000Eh
0x180028210  jmp     loc_1800283B1
0x180028215  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x180028218  mov     ecx, edi; uFlags
0x18002821a  call    cs:__imp_LocalAlloc
0x180028220  mov     r14, rax
0x180028223  test    rax, rax
0x180028226  jz      short loc_18002820B
0x180028228  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002822f  mov     ecx, 60h ; '`'; unsigned __int64
0x180028234  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180028239  mov     rsi, rax
0x18002823c  mov     [rbp+57h+var_40], rax
0x180028240  test    rax, rax
0x180028243  jz      short loc_18002828A
0x180028245  lea     rax, ??_7PersistObject@@6B@; const PersistObject::`vftable'
0x18002824c  mov     [rsi], rax
0x18002824f  mov     [rsi+8], rbx
0x180028253  mov     [rsi+10h], rbx
0x180028257  mov     [rsi+18h], rbx
0x18002825b  lea     rcx, [rsi+20h]; this
0x18002825f  xorps   xmm0, xmm0
0x180028262  xor     eax, eax
0x180028264  movups  xmmword ptr [rcx], xmm0
0x180028267  movups  xmmword ptr [rcx+10h], xmm0
0x18002826b  mov     [rcx+20h], rax
0x18002826f  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180028274  test    eax, eax
0x180028276  js      loc_1800283ED
0x18002827c  mov     [rsi+48h], rbx
0x180028280  mov     [rsi+50h], rbx
0x180028284  mov     [rsi+58h], rbx
0x180028288  jmp     short loc_18002828D
0x18002828a  mov     rsi, rbx
0x18002828d  test    rsi, rsi
0x180028290  jz      loc_18002820B
0x180028296  lea     rbx, [rsi+20h]
0x18002829a  mov     [rbp+57h+var_40], rbx
0x18002829e  mov     rcx, rbx; lpCriticalSection
0x1800282a1  call    cs:__imp_EnterCriticalSection
0x1800282a7  mov     [rbp+57h+var_38], 1
0x1800282ab  lea     r8, [rsi+18h]
0x1800282af  or      edx, 0FFFFFFFFh
0x1800282b2  mov     rcx, r12
0x1800282b5  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800282bb  mov     edi, eax
0x1800282bd  mov     rcx, rbx; lpCriticalSection
0x1800282c0  call    cs:__imp_LeaveCriticalSection
0x1800282c6  test    edi, edi
0x1800282c8  js      loc_18002839E
0x1800282ce  xor     ebx, ebx
0x1800282d0  cmp     [rbp+57h+cValues], ebx
0x1800282d3  jbe     loc_180028393
0x1800282d9  mov     r12, [rbp+57h+hKey]
0x1800282dd  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1800282e0  mov     [rbp+57h+cchValueName], eax
0x1800282e3  mov     eax, dword ptr [rbp+57h+uBytes]
0x1800282e6  mov     dword ptr [rbp+57h+uBytes+4], eax
0x1800282e9  lea     rax, [rbp+57h+uBytes+4]
0x1800282ed  mov     [rsp+0C0h+lpcValues], rax; lpcbData
0x1800282f2  mov     [rsp+0C0h+lpcbMaxClassLen], r14; lpData
0x1800282f7  lea     rax, [rbp+57h+Type]
0x1800282fb  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpType
0x180028300  mov     [rsp+0C0h+lpcSubKeys], 0; lpReserved
0x180028309  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18002830d  mov     r8, r15; lpValueName
0x180028310  mov     edx, ebx; dwIndex
0x180028312  mov     rcx, r12; hKey
0x180028315  call    cs:__imp_RegEnumValueW
0x18002831b  mov     edi, eax
0x18002831d  test    eax, eax
0x18002831f  jnz     loc_1800283E0
0x180028325  lea     r9, [rbp+57h+var_60]
0x180028329  xor     r8d, r8d
0x18002832c  lea     edx, [rax+0Ah]
0x18002832f  mov     rcx, r15
0x180028332  call    cs:__imp_?SafeStringToDword@@YAJPEBGHHPEAK@Z; SafeStringToDword(ushort const *,int,int,ulong *)
0x180028338  mov     edi, eax
0x18002833a  test    eax, eax
0x18002833c  js      short loc_18002839E
0x18002833e  mov     eax, [rbp+57h+Type]
0x180028341  sub     eax, 1
0x180028344  jz      short loc_180028374
0x180028346  sub     eax, 2
0x180028349  jz      short loc_180028360
0x18002834b  cmp     eax, 1
0x18002834e  jnz     short loc_180028399
0x180028350  mov     r8d, [r14]
0x180028353  mov     edx, [rbp+57h+var_60]
0x180028356  mov     rcx, rsi
0x180028359  call    ?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@K@Z; PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,ulong)
0x18002835e  jmp     short loc_180028382
0x180028360  mov     r9d, dword ptr [rbp+57h+uBytes+4]
0x180028364  mov     r8, r14
0x180028367  mov     edx, [rbp+57h+var_60]
0x18002836a  mov     rcx, rsi
0x18002836d  call    ?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@QEAEK@Z; PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,uchar * const,ulong)
0x180028372  jmp     short loc_180028382
0x180028374  mov     r8, r14
0x180028377  mov     edx, [rbp+57h+var_60]
0x18002837a  mov     rcx, rsi
0x18002837d  call    ?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@PEBG@Z; PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,ushort const *)
0x180028382  mov     edi, eax
0x180028384  test    eax, eax
0x180028386  js      short loc_18002839E
0x180028388  inc     ebx
0x18002838a  cmp     ebx, [rbp+57h+cValues]
0x18002838d  jb      loc_1800282DD
0x180028393  mov     [r13+0], rsi
0x180028397  jmp     short loc_1800283B1
0x180028399  mov     edi, 8000FFFFh
0x18002839e  mov     rax, [rsi]
0x1800283a1  mov     edx, 1
0x1800283a6  mov     rcx, rsi
0x1800283a9  mov     rax, [rax]
0x1800283ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283b1  mov     rcx, r15; hMem
0x1800283b4  call    cs:__imp_LocalFree
0x1800283ba  mov     rcx, r14; hMem
0x1800283bd  call    cs:__imp_LocalFree
0x1800283c3  mov     eax, edi
0x1800283c5  mov     rbx, [rsp+0C0h+arg_10]
0x1800283cd  add     rsp, 90h
0x1800283d4  pop     r15
0x1800283d6  pop     r14
0x1800283d8  pop     r13
0x1800283da  pop     r12
0x1800283dc  pop     rdi
0x1800283dd  pop     rsi
0x1800283de  pop     rbp
0x1800283df  retn
0x1800283e0  jle     short loc_18002839E
0x1800283e2  movzx   edi, ax
0x1800283e5  or      edi, 80070000h
0x1800283eb  jmp     short loc_18002839E
0x1800283ed  mov     ecx, eax; int
0x1800283ef  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
