# CServicingSession::SubmitSqmReport(void)

- ea: `0x180025a40`
- end: `0x180025da0`
- name: `?SubmitSqmReport@CServicingSession@@UEAAJXZ`
- size: `864`
- prototype: `__int64 __fastcall(CServicingSession *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007818`
- `0x180025a40`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180025b77`
- `KERNEL32!GetLastError` at `0x180025b77`
- `ntdll!WinSqmSetDWORD64` at `0x180025bee`
- `ntdll!WinSqmSetDWORD64` at `0x180025cbf`
- `ntdll!WinSqmSetDWORD64` at `0x180025d41`
- `ntdll!WinSqmSetDWORD64` at `0x180025d75`
- `ntdll!WinSqmSetDWORD64` at `0x180025bee`
- `ntdll!WinSqmSetDWORD64` at `0x180025cbf`
- `ntdll!WinSqmSetDWORD64` at `0x180025d41`
- `ntdll!WinSqmSetDWORD64` at `0x180025d75`
- `ntdll!WinSqmStartSession` at `0x180025b68`
- `ntdll!WinSqmStartSession` at `0x180025b68`
- `ntdll!WinSqmSetDWORD` at `0x180025bbf`
- `ntdll!WinSqmSetDWORD` at `0x180025c13`
- `ntdll!WinSqmSetDWORD` at `0x180025c32`
- `ntdll!WinSqmSetDWORD` at `0x180025c4d`
- `ntdll!WinSqmSetDWORD` at `0x180025c62`
- `ntdll!WinSqmSetDWORD` at `0x180025c81`
- `ntdll!WinSqmSetDWORD` at `0x180025c9b`
- `ntdll!WinSqmSetDWORD` at `0x180025cd9`
- `ntdll!WinSqmSetDWORD` at `0x180025cf3`
- `ntdll!WinSqmSetDWORD` at `0x180025d0d`
- `ntdll!WinSqmSetDWORD` at `0x180025d27`
- `ntdll!WinSqmSetDWORD` at `0x180025d5b`
- `ntdll!WinSqmSetDWORD` at `0x180025bbf`
- `ntdll!WinSqmSetDWORD` at `0x180025c13`
- `ntdll!WinSqmSetDWORD` at `0x180025c32`
- `ntdll!WinSqmSetDWORD` at `0x180025c4d`
- `ntdll!WinSqmSetDWORD` at `0x180025c62`
- `ntdll!WinSqmSetDWORD` at `0x180025c81`
- `ntdll!WinSqmSetDWORD` at `0x180025c9b`
- `ntdll!WinSqmSetDWORD` at `0x180025cd9`
- `ntdll!WinSqmSetDWORD` at `0x180025cf3`
- `ntdll!WinSqmSetDWORD` at `0x180025d0d`
- `ntdll!WinSqmSetDWORD` at `0x180025d27`
- `ntdll!WinSqmSetDWORD` at `0x180025d5b`
- `ntdll!WinSqmIsOptedIn` at `0x180025a6f`
- `ntdll!WinSqmIsOptedIn` at `0x180025a6f`
- `ntdll!WinSqmEndSession` at `0x180025d7e`
- `ntdll!WinSqmEndSession` at `0x180025d7e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180025b11`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180025b11`

## pseudocode

```c
__int64 __fastcall CServicingSession::SubmitSqmReport(CServicingSession *this)
{
  unsigned int v3; // r15d
  __int64 v4; // rbx
  __int64 v5; // rcx
  unsigned int v6; // edx
  __int64 v7; // rbx
  __int64 v8; // r8
  __int64 v9; // r14
  unsigned int v10; // ebp
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 started; // rax
  __int64 v14; // rsi
  signed int LastError; // eax
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // r8
  __int64 v26; // r8
  int v27; // [rsp+20h] [rbp-68h] BYREF
  __int64 v28; // [rsp+28h] [rbp-60h]
  GUID pguid; // [rsp+30h] [rbp-58h] BYREF

  v27 = 0;
  pguid = 0;
  if ( !(unsigned int)WinSqmIsOptedIn() )
    return 1;
  v3 = 0;
  if ( (*(int (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 2) + 80LL))(*((_QWORD *)this + 2), &v27) >= 0 )
  {
    if ( v27 )
    {
      if ( v27 == 1 )
      {
        v3 = 4;
      }
      else if ( v27 == 2 )
      {
        v3 = 3;
      }
    }
    else
    {
      v3 = 1;
    }
  }
  v4 = *((_QWORD *)this + 45);
  v5 = *((unsigned int *)this + 88);
  LODWORD(v28) = *((_DWORD *)this + 88);
  v6 = *((_DWORD *)this + 89);
  HIDWORD(v28) = v6;
  v7 = v4 - v28;
  if ( v7 <= 0 )
    v7 = 0;
  v8 = *((_QWORD *)this + 16);
  if ( v8 )
    v9 = v5 + ((unsigned __int64)v6 << 32) - v8;
  else
    v9 = 0;
  v10 = CoCreateGuid(&pguid);
  if ( (v10 & 0x80000000) != 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v10;
    v12 = 15;
    goto LABEL_19;
  }
  started = WinSqmStartSession(&pguid, 101457953, 0);
  v14 = started;
  if ( started != -1 )
  {
    WinSqmSetDWORD(started, 9228, v3);
    WinSqmSetDWORD64(v14, 9229, v9 / 10000000 + v9);
    WinSqmSetDWORD(v14, 9230, v7 / 10000000 + v7);
    WinSqmSetDWORD(v14, 9231, (unsigned int)(*((_DWORD *)this + 40) != 0) + 1);
    v16 = *((unsigned int *)this + 94);
    if ( (_DWORD)v16 != -1 )
      WinSqmSetDWORD(v14, 9232, v16);
    WinSqmSetDWORD(v14, 9233, *((unsigned int *)this + 58));
    v17 = *((unsigned int *)this + 98);
    if ( (_DWORD)v17 != 0x7FFFFFFF )
      WinSqmSetDWORD(v14, 9234, v17);
    v18 = *((unsigned int *)this + 99);
    if ( (_DWORD)v18 != 0x7FFFFFFF )
      WinSqmSetDWORD(v14, 9235, v18);
    v19 = *((_QWORD *)this + 52);
    if ( v19 != 0x7FFFFFFFFFFFFFFFLL )
      WinSqmSetDWORD64(v14, 9236, v19);
    v20 = *((unsigned int *)this + 95);
    if ( (_DWORD)v20 != 0x7FFFFFFF )
      WinSqmSetDWORD(v14, 9237, v20);
    v21 = *((unsigned int *)this + 92);
    if ( (_DWORD)v21 != 0x7FFFFFFF )
      WinSqmSetDWORD(v14, 9238, v21);
    v22 = *((unsigned int *)this + 93);
    if ( (_DWORD)v22 != 0x7FFFFFFF )
      WinSqmSetDWORD(v14, 9239, v22);
    v23 = *((unsigned int *)this + 96);
    if ( (_DWORD)v23 != 0x7FFFFFFF )
      WinSqmSetDWORD(v14, 9249, v23);
    v24 = *((_QWORD *)this + 50);
    if ( v24 != 0x7FFFFFFFFFFFFFFFLL )
      WinSqmSetDWORD64(v14, 9248, v24);
    v25 = *((unsigned int *)this + 97);
    if ( (_DWORD)v25 != 0x7FFFFFFF )
      WinSqmSetDWORD(v14, 9251, v25);
    v26 = *((_QWORD *)this + 51);
    if ( v26 != 0x7FFFFFFFFFFFFFFFLL )
      WinSqmSetDWORD64(v14, 9250, v26);
    WinSqmEndSession(v14);
    return v10;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 16;
LABEL_19:
    WPP_SF_d(v11[2], v12, WPP_99859d014f2c3b7a1651f9c2c88a152b_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180025a40  push    rbx
0x180025a42  push    rbp
0x180025a43  push    rsi
0x180025a44  push    rdi
0x180025a45  push    r14
0x180025a47  push    r15
0x180025a49  sub     rsp, 58h
0x180025a4d  mov     rax, cs:__security_cookie
0x180025a54  xor     rax, rsp
0x180025a57  mov     [rsp+88h+var_48], rax
0x180025a5c  mov     rdi, rcx
0x180025a5f  mov     [rsp+88h+var_68], 0
0x180025a67  xorps   xmm0, xmm0
0x180025a6a  movups  xmmword ptr [rsp+88h+pguid.Data1], xmm0
0x180025a6f  call    cs:__imp_WinSqmIsOptedIn
0x180025a75  test    eax, eax
0x180025a77  jnz     short loc_180025A83
0x180025a79  mov     eax, 1
0x180025a7e  jmp     loc_180025D86
0x180025a83  mov     rcx, [rdi+10h]
0x180025a87  mov     rax, [rcx]
0x180025a8a  lea     rdx, [rsp+88h+var_68]
0x180025a8f  mov     rax, [rax+50h]
0x180025a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a98  xor     r15d, r15d
0x180025a9b  test    eax, eax
0x180025a9d  js      short loc_180025AC5
0x180025a9f  mov     ecx, [rsp+88h+var_68]
0x180025aa3  test    ecx, ecx
0x180025aa5  jz      short loc_180025ABF
0x180025aa7  sub     ecx, 1
0x180025aaa  jz      short loc_180025AB7
0x180025aac  cmp     ecx, 1
0x180025aaf  jnz     short loc_180025AC5
0x180025ab1  lea     r15d, [rcx+2]
0x180025ab5  jmp     short loc_180025AC5
0x180025ab7  mov     r15d, 4
0x180025abd  jmp     short loc_180025AC5
0x180025abf  mov     r15d, 1
0x180025ac5  mov     rbx, [rdi+168h]
0x180025acc  mov     ecx, [rdi+160h]
0x180025ad2  mov     dword ptr [rsp+88h+var_60], ecx
0x180025ad6  mov     edx, [rdi+164h]
0x180025adc  mov     dword ptr [rsp+88h+var_60+4], edx
0x180025ae0  sub     rbx, [rsp+88h+var_60]
0x180025ae5  xor     eax, eax
0x180025ae7  test    rbx, rbx
0x180025aea  cmovle  rbx, rax
0x180025aee  mov     r8, [rdi+80h]
0x180025af5  test    r8, r8
0x180025af8  jz      short loc_180025B09
0x180025afa  mov     r14d, edx
0x180025afd  shl     r14, 20h
0x180025b01  add     r14, rcx
0x180025b04  sub     r14, r8
0x180025b07  jmp     short loc_180025B0C
0x180025b09  xor     r14d, r14d
0x180025b0c  lea     rcx, [rsp+88h+pguid]; pguid
0x180025b11  call    cs:__imp_CoCreateGuid
0x180025b17  mov     ebp, eax
0x180025b19  test    eax, eax
0x180025b1b  jns     short loc_180025B5B
0x180025b1d  lea     rax, WPP_GLOBAL_Control
0x180025b24  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b2b  cmp     rcx, rax
0x180025b2e  jz      loc_180025D84
0x180025b34  test    byte ptr [rcx+1Ch], 1
0x180025b38  jz      loc_180025D84
0x180025b3e  mov     edx, 0Fh
0x180025b43  mov     r9d, ebp
0x180025b46  lea     r8, WPP_99859d014f2c3b7a1651f9c2c88a152b_Traceguids
0x180025b4d  mov     rcx, [rcx+10h]
0x180025b51  call    WPP_SF_d
0x180025b56  jmp     loc_180025D84
0x180025b5b  xor     r8d, r8d
0x180025b5e  mov     edx, 60C2021h
0x180025b63  lea     rcx, [rsp+88h+pguid]
0x180025b68  call    cs:__imp_WinSqmStartSession
0x180025b6e  mov     rsi, rax
0x180025b71  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025b75  jnz     short loc_180025BB4
0x180025b77  call    cs:__imp_GetLastError
0x180025b7d  mov     ebp, eax
0x180025b7f  test    eax, eax
0x180025b81  jle     short loc_180025B8C
0x180025b83  movzx   ebp, ax
0x180025b86  or      ebp, 80070000h
0x180025b8c  lea     rax, WPP_GLOBAL_Control
0x180025b93  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b9a  cmp     rcx, rax
0x180025b9d  jz      loc_180025D84
0x180025ba3  test    byte ptr [rcx+1Ch], 1
0x180025ba7  jz      loc_180025D84
0x180025bad  mov     edx, 10h
0x180025bb2  jmp     short loc_180025B43
0x180025bb4  mov     r8d, r15d
0x180025bb7  mov     edx, 240Ch
0x180025bbc  mov     rcx, rsi
0x180025bbf  call    cs:__imp_WinSqmSetDWORD
0x180025bc5  mov     r15, 0D6BF94D5E57A42BDh
0x180025bcf  mov     rax, r15
0x180025bd2  imul    r14
0x180025bd5  add     rdx, r14
0x180025bd8  sar     rdx, 17h
0x180025bdc  mov     r8, rdx
0x180025bdf  shr     r8, 3Fh
0x180025be3  add     r8, rdx
0x180025be6  mov     edx, 240Dh
0x180025beb  mov     rcx, rsi
0x180025bee  call    cs:__imp_WinSqmSetDWORD64
0x180025bf4  mov     rax, r15
0x180025bf7  imul    rbx
0x180025bfa  add     rdx, rbx
0x180025bfd  sar     rdx, 17h
0x180025c01  mov     r8, rdx
0x180025c04  shr     r8, 3Fh
0x180025c08  add     r8, rdx
0x180025c0b  mov     edx, 240Eh
0x180025c10  mov     rcx, rsi
0x180025c13  call    cs:__imp_WinSqmSetDWORD
0x180025c19  mov     eax, [rdi+0A0h]
0x180025c1f  neg     eax
0x180025c21  sbb     r8d, r8d
0x180025c24  neg     r8d
0x180025c27  inc     r8d
0x180025c2a  mov     edx, 240Fh
0x180025c2f  mov     rcx, rsi
0x180025c32  call    cs:__imp_WinSqmSetDWORD
0x180025c38  mov     r8d, [rdi+178h]
0x180025c3f  cmp     r8d, 0FFFFFFFFh
0x180025c43  jz      short loc_180025C53
0x180025c45  mov     edx, 2410h
0x180025c4a  mov     rcx, rsi
0x180025c4d  call    cs:__imp_WinSqmSetDWORD
0x180025c53  mov     r8d, [rdi+0E8h]
0x180025c5a  mov     edx, 2411h
0x180025c5f  mov     rcx, rsi
0x180025c62  call    cs:__imp_WinSqmSetDWORD
0x180025c68  mov     r8d, [rdi+188h]
0x180025c6f  mov     ebx, 7FFFFFFFh
0x180025c74  cmp     r8d, ebx
0x180025c77  jz      short loc_180025C87
0x180025c79  mov     edx, 2412h
0x180025c7e  mov     rcx, rsi
0x180025c81  call    cs:__imp_WinSqmSetDWORD
0x180025c87  mov     r8d, [rdi+18Ch]
0x180025c8e  cmp     r8d, ebx
0x180025c91  jz      short loc_180025CA1
0x180025c93  mov     edx, 2413h
0x180025c98  mov     rcx, rsi
0x180025c9b  call    cs:__imp_WinSqmSetDWORD
0x180025ca1  mov     r8, [rdi+1A0h]
0x180025ca8  mov     r14, 7FFFFFFFFFFFFFFFh
0x180025cb2  cmp     r8, r14
0x180025cb5  jz      short loc_180025CC5
0x180025cb7  mov     edx, 2414h
0x180025cbc  mov     rcx, rsi
0x180025cbf  call    cs:__imp_WinSqmSetDWORD64
0x180025cc5  mov     r8d, [rdi+17Ch]
0x180025ccc  cmp     r8d, ebx
0x180025ccf  jz      short loc_180025CDF
0x180025cd1  mov     edx, 2415h
0x180025cd6  mov     rcx, rsi
0x180025cd9  call    cs:__imp_WinSqmSetDWORD
0x180025cdf  mov     r8d, [rdi+170h]
0x180025ce6  cmp     r8d, ebx
0x180025ce9  jz      short loc_180025CF9
0x180025ceb  mov     edx, 2416h
0x180025cf0  mov     rcx, rsi
0x180025cf3  call    cs:__imp_WinSqmSetDWORD
0x180025cf9  mov     r8d, [rdi+174h]
0x180025d00  cmp     r8d, ebx
0x180025d03  jz      short loc_180025D13
0x180025d05  mov     edx, 2417h
0x180025d0a  mov     rcx, rsi
0x180025d0d  call    cs:__imp_WinSqmSetDWORD
0x180025d13  mov     r8d, [rdi+180h]
0x180025d1a  cmp     r8d, ebx
0x180025d1d  jz      short loc_180025D2D
0x180025d1f  mov     edx, 2421h
0x180025d24  mov     rcx, rsi
0x180025d27  call    cs:__imp_WinSqmSetDWORD
0x180025d2d  mov     r8, [rdi+190h]
0x180025d34  cmp     r8, r14
0x180025d37  jz      short loc_180025D47
0x180025d39  mov     edx, 2420h
0x180025d3e  mov     rcx, rsi
0x180025d41  call    cs:__imp_WinSqmSetDWORD64
0x180025d47  mov     r8d, [rdi+184h]
0x180025d4e  cmp     r8d, ebx
0x180025d51  jz      short loc_180025D61
0x180025d53  mov     edx, 2423h
0x180025d58  mov     rcx, rsi
0x180025d5b  call    cs:__imp_WinSqmSetDWORD
0x180025d61  mov     r8, [rdi+198h]
0x180025d68  cmp     r8, r14
0x180025d6b  jz      short loc_180025D7B
0x180025d6d  mov     edx, 2422h
0x180025d72  mov     rcx, rsi
0x180025d75  call    cs:__imp_WinSqmSetDWORD64
0x180025d7b  mov     rcx, rsi
0x180025d7e  call    cs:__imp_WinSqmEndSession
0x180025d84  mov     eax, ebp
0x180025d86  mov     rcx, [rsp+88h+var_48]
0x180025d8b  xor     rcx, rsp; StackCookie
0x180025d8e  call    __security_check_cookie
0x180025d93  add     rsp, 58h
0x180025d97  pop     r15
0x180025d99  pop     r14
0x180025d9b  pop     rdi
0x180025d9c  pop     rsi
0x180025d9d  pop     rbp
0x180025d9e  pop     rbx
0x180025d9f  retn
```
