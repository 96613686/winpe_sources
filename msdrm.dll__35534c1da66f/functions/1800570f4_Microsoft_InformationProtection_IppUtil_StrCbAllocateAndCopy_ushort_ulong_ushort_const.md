# Microsoft::InformationProtection::IppUtil::StrCbAllocateAndCopy(ushort * *,ulong *,ushort const *)

- ea: `0x1800570f4`
- end: `0x180057339`
- name: `?StrCbAllocateAndCopy@IppUtil@InformationProtection@Microsoft@@SAXPEAPEAGPEAKPEBG@Z`
- size: `581`
- prototype: `void __fastcall(unsigned __int16 **, unsigned int *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180052440`
- `0x1800527e0`

## callees

- `0x180001244`
- `0x180001284`
- `0x18000343a`
- `0x180015438`
- `0x1800516b8`
- `0x1800570f4`
- `0x18005bd72`
- `0x18005bdc0`

## string_xrefs

- `0x1800572ae`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\ipputil.cpp`
- `0x180057316`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\ipputil.cpp`
- `0x180057309`: `StringCbCopy(wszDest, cbDest, wszSrc)`
- `0x1800572e2`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\auto_ipcmem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::InformationProtection::IppUtil::StrCbAllocateAndCopy(
        unsigned __int16 **a1,
        unsigned int *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // rdi
  __int64 v6; // r9
  const unsigned __int16 *v7; // rax
  int v8; // ebx
  int v9; // ecx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdx
  unsigned int v14; // ebp
  void *v15; // rsi
  unsigned __int64 v16; // rdx
  __int64 v17; // rax
  unsigned __int16 *v18; // r8
  unsigned __int16 v19; // cx
  unsigned __int16 *v20; // rcx
  _BYTE pExceptionObject[1216]; // [rsp+40h] [rbp-4F8h] BYREF

  v3 = a3;
  if ( !a3 )
  {
    v9 = -2147024809;
    goto LABEL_24;
  }
  v6 = 0x7FFFFFFF;
  v7 = a3;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = -2147024809;
  v9 = v6 == 0 ? 0x80070057 : 0;
  v10 = (0x7FFFFFFF - v6) & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64);
  if ( !v6 )
  {
LABEL_24:
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\ipputil.cpp",
      0xB0u,
      L"StringCchLength(wszSrc, STRSAFE_MAX_CCH, &lenSrc)",
      v9);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  v11 = v10 + 1;
  if ( v10 + 1 < v10 )
    goto LABEL_22;
  if ( HIDWORD(v11) )
  {
    if ( (v11 & 0x8000000000000000uLL) != 0LL
      || (v12 = 2LL * (unsigned int)v11, v13 = HIDWORD(v11) << 33, v11 = v13 + v12, v13 + v12 < v12) )
    {
LABEL_22:
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v11);
    }
  }
  else
  {
    v11 = 2LL * (unsigned int)v11;
  }
  if ( v11 > 0xFFFFFFFF )
    goto LABEL_22;
  v14 = v11;
  v15 = operator new((unsigned int)v11);
  memset_0(v15, 0, v14);
  if ( !v15 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\auto_ipcmem.h",
      0x49u,
      L"p",
      -2147024809);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  operator delete(0);
  v16 = (unsigned __int64)v14 >> 1;
  if ( !v16 )
    goto LABEL_26;
  v17 = 2147483646;
  v18 = (unsigned __int16 *)v15;
  do
  {
    if ( !v17 )
      break;
    v19 = *v3;
    if ( !*v3 )
      break;
    ++v3;
    *v18++ = v19;
    --v17;
    --v16;
  }
  while ( v16 );
  v20 = v18 - 1;
  if ( v16 )
    v20 = v18;
  *v20 = 0;
  v8 = v16 == 0 ? 0x8007007A : 0;
  if ( !v16 )
  {
LABEL_26:
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\ipputil.cpp",
      0xB3u,
      L"StringCbCopy(wszDest, cbDest, wszSrc)",
      v8);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  *a1 = (unsigned __int16 *)v15;
  *a2 = v14;
  operator delete(0);
}

```

## disassembly

```asm
0x1800570f4  mov     rax, rsp
0x1800570f7  push    rsi
0x1800570f8  push    rdi
0x1800570f9  push    r12
0x1800570fb  push    r14
0x1800570fd  push    r15
0x1800570ff  sub     rsp, 510h
0x180057106  mov     [rsp+538h+var_508], 0FFFFFFFFFFFFFFFEh
0x18005710f  mov     [rax+18h], rbx
0x180057113  mov     [rax+20h], rbp
0x180057117  mov     rax, cs:__security_cookie
0x18005711e  xor     rax, rsp
0x180057121  mov     [rsp+538h+var_38], rax
0x180057129  mov     rdi, r8
0x18005712c  mov     r15, rdx
0x18005712f  mov     r14, rcx
0x180057132  xor     r12d, r12d
0x180057135  test    r8, r8
0x180057138  jz      loc_180057298
0x18005713e  mov     r10d, 7FFFFFFFh
0x180057144  mov     r9d, r10d
0x180057147  mov     rax, r8
0x18005714a  cmp     [rax], r12w
0x18005714e  jz      short loc_18005715A
0x180057150  add     rax, 2
0x180057154  sub     r9, 1
0x180057158  jnz     short loc_18005714A
0x18005715a  mov     rax, r9
0x18005715d  neg     rax
0x180057160  sbb     ecx, ecx
0x180057162  not     ecx
0x180057164  mov     ebx, 80070057h
0x180057169  and     ecx, ebx
0x18005716b  mov     rax, r9
0x18005716e  sub     r10, r9
0x180057171  neg     rax
0x180057174  sbb     rdx, rdx
0x180057177  and     rdx, r10
0x18005717a  test    r9, r9
0x18005717d  jz      loc_18005729D
0x180057183  lea     rcx, [rdx+1]
0x180057187  cmp     rcx, rdx
0x18005718a  jb      loc_180057292
0x180057190  mov     rax, rcx
0x180057193  shr     rax, 20h
0x180057197  test    eax, eax
0x180057199  jnz     short loc_1800571A2
0x18005719b  mov     ecx, ecx
0x18005719d  add     rcx, rcx
0x1800571a0  jmp     short loc_1800571C3
0x1800571a2  mov     rdx, rax
0x1800571a5  test    eax, eax
0x1800571a7  js      loc_180057292
0x1800571ad  mov     eax, ecx
0x1800571af  add     rax, rax
0x1800571b2  shl     rdx, 21h
0x1800571b6  lea     rcx, [rdx+rax]
0x1800571ba  cmp     rcx, rax
0x1800571bd  jb      loc_180057292
0x1800571c3  mov     eax, 0FFFFFFFFh
0x1800571c8  cmp     rcx, rax
0x1800571cb  ja      loc_180057292
0x1800571d1  mov     ebp, ecx
0x1800571d3  mov     ecx, ecx; Size
0x1800571d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800571da  mov     rsi, rax
0x1800571dd  mov     r8d, ebp; Size
0x1800571e0  xor     edx, edx; Val
0x1800571e2  mov     rcx, rax; void *
0x1800571e5  call    memset_0
0x1800571ea  test    rsi, rsi
0x1800571ed  jz      loc_1800572D1
0x1800571f3  xor     ecx, ecx; Block
0x1800571f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800571fa  mov     [rsp+538h+var_500], rsi
0x1800571ff  mov     edx, ebp
0x180057201  shr     rdx, 1
0x180057204  jz      loc_180057305
0x18005720a  mov     eax, 7FFFFFFEh
0x18005720f  mov     r8, rsi
0x180057212  test    rax, rax
0x180057215  jz      short loc_180057234
0x180057217  movzx   ecx, word ptr [rdi]
0x18005721a  test    cx, cx
0x18005721d  jz      short loc_180057234
0x18005721f  add     rdi, 2
0x180057223  mov     [r8], cx
0x180057227  add     r8, 2
0x18005722b  dec     rax
0x18005722e  sub     rdx, 1
0x180057232  jnz     short loc_180057212
0x180057234  mov     rax, rdx
0x180057237  neg     rax
0x18005723a  sbb     ebx, ebx
0x18005723c  not     ebx
0x18005723e  lea     rcx, [r8-2]
0x180057242  test    rdx, rdx
0x180057245  cmovnz  rcx, r8
0x180057249  mov     [rcx], r12w
0x18005724d  and     ebx, 8007007Ah
0x180057253  js      loc_180057305
0x180057259  mov     [r14], rsi
0x18005725c  mov     [r15], ebp
0x18005725f  xor     ecx, ecx; Block
0x180057261  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180057266  mov     rcx, [rsp+538h+var_38]
0x18005726e  xor     rcx, rsp; StackCookie
0x180057271  call    __security_check_cookie
0x180057276  lea     r11, [rsp+538h+var_28]
0x18005727e  mov     rbx, [r11+40h]
0x180057282  mov     rbp, [r11+48h]
0x180057286  mov     rsp, r11
0x180057289  pop     r15
0x18005728b  pop     r14
0x18005728d  pop     r12
0x18005728f  pop     rdi
0x180057290  pop     rsi
0x180057291  retn
0x180057292  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180057298  mov     ecx, 80070057h
0x18005729d  mov     [rsp+538h+var_518], ecx; int
0x1800572a1  lea     r9, aStringcchlengt; "StringCchLength(wszSrc, STRSAFE_MAX_CCH"...
0x1800572a8  mov     r8d, 0B0h; unsigned int
0x1800572ae  lea     rdx, aDsSecurityRmSr; "ds\\security\\rm\\src\\client\\promethi"...
0x1800572b5  lea     rcx, [rsp+538h+pExceptionObject]; this
0x1800572ba  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800572bf  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x1800572c6  lea     rcx, [rsp+538h+pExceptionObject]; pExceptionObject
0x1800572cb  call    _CxxThrowException_0
0x1800572d1  mov     [rsp+538h+var_518], ebx; int
0x1800572d5  lea     r9, aP; "p"
0x1800572dc  mov     r8d, 49h ; 'I'; unsigned int
0x1800572e2  lea     rdx, aDsSecurityRmSr_1; "ds\\security\\rm\\src\\client\\promethi"...
0x1800572e9  lea     rcx, [rsp+538h+pExceptionObject]; this
0x1800572ee  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800572f3  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x1800572fa  lea     rcx, [rsp+538h+pExceptionObject]; pExceptionObject
0x1800572ff  call    _CxxThrowException_0
0x180057305  mov     [rsp+538h+var_518], ebx; int
0x180057309  lea     r9, aStringcbcopyWs; "StringCbCopy(wszDest, cbDest, wszSrc)"
0x180057310  mov     r8d, 0B3h; unsigned int
0x180057316  lea     rdx, aDsSecurityRmSr; "ds\\security\\rm\\src\\client\\promethi"...
0x18005731d  lea     rcx, [rsp+538h+pExceptionObject]; this
0x180057322  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180057327  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x18005732e  lea     rcx, [rsp+538h+pExceptionObject]; pExceptionObject
0x180057333  call    _CxxThrowException_0
```
