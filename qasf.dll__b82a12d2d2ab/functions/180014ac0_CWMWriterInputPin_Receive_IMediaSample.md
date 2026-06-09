# CWMWriterInputPin::Receive(IMediaSample *)

- ea: `0x180014ac0`
- end: `0x180014cae`
- name: `?Receive@CWMWriterInputPin@@UEAAJPEAUIMediaSample@@@Z`
- size: `494`
- prototype: `__int64 __fastcall(CWMWriterInputPin *__hidden this, struct IMediaSample *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001460`
- `0x180005b6c`
- `0x1800100f4`
- `0x180010dfc`
- `0x180014ac0`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180014af7`
- `KERNEL32!EnterCriticalSection` at `0x180014af7`
- `KERNEL32!LeaveCriticalSection` at `0x180014c81`
- `KERNEL32!LeaveCriticalSection` at `0x180014c81`
- `KERNEL32!WaitForSingleObject` at `0x180014bfc`
- `KERNEL32!WaitForSingleObject` at `0x180014bfc`
- `KERNEL32!ResetEvent` at `0x180014bef`
- `KERNEL32!ResetEvent` at `0x180014bef`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::Receive(CWMWriterInputPin *this, struct IMediaSample *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r12
  unsigned int v5; // edi
  bool v6; // zf
  _QWORD *v7; // rsi
  __int64 v8; // rdi
  int v9; // eax
  bool v10; // sf
  int v11; // r15d
  int v12; // eax
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v19; // [rsp+30h] [rbp-20h] BYREF
  __int64 v20; // [rsp+38h] [rbp-18h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v5 = CBaseInputPin::Receive(this, a2);
  if ( !v5 )
  {
    v6 = (*((_BYTE *)this + 32) & 8) == 0;
    v7 = (_QWORD *)((char *)this - 216);
    v20 = 0;
    v19 = 0;
    if ( !v6 )
    {
      v8 = *((_QWORD *)this + 8);
      v9 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v7[3] + 88LL))(v7 + 3, v8);
      v10 = v9 < 0;
      if ( !v9 )
      {
        v9 = (*(__int64 (__fastcall **)(char *, __int64))(*v7 + 72LL))((char *)this - 216, v8);
        v10 = v9 < 0;
      }
      if ( v10 )
        goto LABEL_16;
    }
    v11 = ((__int64 (__fastcall *)(struct IMediaSample *))a2->lpVtbl->GetActualDataLength)(a2);
    v12 = ((__int64 (__fastcall *)(struct IMediaSample *, __int64 *, __int64 *))a2->lpVtbl->GetTime)(a2, &v20, &v19);
    v5 = v12;
    if ( v12 >= 0 )
    {
      v13 = v20;
      v14 = *((_DWORD *)this + 63);
      v7[60] = v20;
      if ( !v14 && v13 < 0 )
        *((_QWORD *)this + 32) = v13;
      *((_DWORD *)this + 63) = v14 + 1;
      v15 = *((_QWORD *)this + 32);
      v19 -= v15;
      v16 = v13 - v15;
      v20 = v16;
      if ( v11 )
      {
        if ( (unsigned int)CWMWriter::HaveIDeliveredTooMuch(
                             *((CWMWriter **)this + 16),
                             (CWMWriterInputPin *)((char *)this - 216),
                             v16) )
        {
          ResetEvent(*((HANDLE *)this + 15));
          WaitForSingleObject(*((HANDLE *)this + 15), 0xFFFFFFFF);
        }
        if ( v19 < v20 )
          v19 = v20 + 1;
        v9 = CWMWriter::Receive(*((CWMWriter **)this + 16), (CWMWriterInputPin *)((char *)this - 216), a2, &v20, &v19);
LABEL_16:
        v5 = v9;
        goto LABEL_22;
      }
LABEL_19:
      v5 = 0;
      goto LABEL_22;
    }
    if ( !v11 || v12 == -2147220919 )
      goto LABEL_19;
    *(_DWORD *)(*((_QWORD *)this + 16) + 300LL) = 1;
    v17 = *(_QWORD *)(*((_QWORD *)this + 16) + 104LL);
    if ( v17 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v17 + 24LL))(v17, 3, v12);
  }
LABEL_22:
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x180014ac0  mov     [rsp-28h+arg_10], rbx
0x180014ac5  mov     [rsp-28h+arg_18], rsi
0x180014aca  push    rbp
0x180014acb  push    rdi
0x180014acc  push    r12
0x180014ace  push    r14
0x180014ad0  push    r15
0x180014ad2  mov     rbp, rsp
0x180014ad5  sub     rsp, 50h
0x180014ad9  mov     rax, cs:__security_cookie
0x180014ae0  xor     rax, rsp
0x180014ae3  mov     [rbp+var_10], rax
0x180014ae7  lea     r12, [rcx+88h]
0x180014aee  mov     rbx, rcx
0x180014af1  mov     rcx, r12; lpCriticalSection
0x180014af4  mov     r14, rdx
0x180014af7  call    cs:__imp_EnterCriticalSection
0x180014afd  mov     rdx, r14; struct IMediaSample *
0x180014b00  mov     rcx, rbx; this
0x180014b03  call    ?Receive@CBaseInputPin@@UEAAJPEAUIMediaSample@@@Z; CBaseInputPin::Receive(IMediaSample *)
0x180014b08  mov     edi, eax
0x180014b0a  test    eax, eax
0x180014b0c  jnz     loc_180014C7E
0x180014b12  test    byte ptr [rbx+20h], 8
0x180014b16  lea     rsi, [rbx-0D8h]
0x180014b1d  mov     [rbp+var_18], 0
0x180014b25  mov     [rbp+var_20], 0
0x180014b2d  jz      short loc_180014B64
0x180014b2f  mov     rdi, [rbx+40h]
0x180014b33  lea     rcx, [rsi+18h]
0x180014b37  mov     rax, [rcx]
0x180014b3a  mov     rdx, rdi
0x180014b3d  mov     rax, [rax+58h]
0x180014b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b46  test    eax, eax
0x180014b48  jnz     short loc_180014B5E
0x180014b4a  mov     rax, [rsi]
0x180014b4d  mov     rdx, rdi
0x180014b50  mov     rcx, rsi
0x180014b53  mov     rax, [rax+48h]
0x180014b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b5c  test    eax, eax
0x180014b5e  js      loc_180014C32
0x180014b64  mov     rax, [r14]
0x180014b67  mov     rcx, r14
0x180014b6a  mov     rax, [rax+58h]
0x180014b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b73  mov     rcx, [r14]
0x180014b76  lea     r8, [rbp+var_20]
0x180014b7a  mov     r15d, eax
0x180014b7d  lea     rdx, [rbp+var_18]
0x180014b81  mov     rax, [rcx+28h]
0x180014b85  mov     rcx, r14
0x180014b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b8d  movsxd  rdi, eax
0x180014b90  test    eax, eax
0x180014b92  js      loc_180014C36
0x180014b98  mov     r8, [rbp+var_18]
0x180014b9c  mov     eax, [rbx+0FCh]
0x180014ba2  mov     [rsi+1E0h], r8
0x180014ba9  test    eax, eax
0x180014bab  jnz     short loc_180014BB9
0x180014bad  test    r8, r8
0x180014bb0  jns     short loc_180014BB9
0x180014bb2  mov     [rbx+100h], r8
0x180014bb9  inc     eax
0x180014bbb  mov     [rbx+0FCh], eax
0x180014bc1  mov     rax, [rbx+100h]
0x180014bc8  sub     [rbp+var_20], rax
0x180014bcc  sub     r8, rax; __int64
0x180014bcf  mov     [rbp+var_18], r8
0x180014bd3  test    r15d, r15d
0x180014bd6  jz      short loc_180014C43
0x180014bd8  mov     rcx, [rbx+80h]; this
0x180014bdf  mov     rdx, rsi; struct CWMWriterInputPin *
0x180014be2  call    ?HaveIDeliveredTooMuch@CWMWriter@@AEAAHPEAVCWMWriterInputPin@@_J@Z; CWMWriter::HaveIDeliveredTooMuch(CWMWriterInputPin *,__int64)
0x180014be7  test    eax, eax
0x180014be9  jz      short loc_180014C02
0x180014beb  mov     rcx, [rbx+78h]; hEvent
0x180014bef  call    cs:__imp_ResetEvent
0x180014bf5  mov     rcx, [rbx+78h]; hHandle
0x180014bf9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014bfc  call    cs:__imp_WaitForSingleObject
0x180014c02  mov     rax, [rbp+var_18]
0x180014c06  cmp     [rbp+var_20], rax
0x180014c0a  jge     short loc_180014C13
0x180014c0c  inc     rax
0x180014c0f  mov     [rbp+var_20], rax
0x180014c13  mov     rcx, [rbx+80h]; this
0x180014c1a  lea     rax, [rbp+var_20]
0x180014c1e  lea     r9, [rbp+var_18]; __int64 *
0x180014c22  mov     [rsp+50h+var_30], rax; __int64 *
0x180014c27  mov     r8, r14; struct IMediaSample *
0x180014c2a  mov     rdx, rsi; struct CWMWriterInputPin *
0x180014c2d  call    ?Receive@CWMWriter@@IEAAJPEAVCWMWriterInputPin@@PEAUIMediaSample@@PEA_J2@Z; CWMWriter::Receive(CWMWriterInputPin *,IMediaSample *,__int64 *,__int64 *)
0x180014c32  mov     edi, eax
0x180014c34  jmp     short loc_180014C7E
0x180014c36  test    r15d, r15d
0x180014c39  jz      short loc_180014C43
0x180014c3b  cmp     edi, 80040249h
0x180014c41  jnz     short loc_180014C47
0x180014c43  xor     edi, edi
0x180014c45  jmp     short loc_180014C7E
0x180014c47  mov     rax, [rbx+80h]
0x180014c4e  mov     dword ptr [rax+12Ch], 1
0x180014c58  mov     rax, [rbx+80h]
0x180014c5f  mov     rcx, [rax+68h]
0x180014c63  test    rcx, rcx
0x180014c66  jz      short loc_180014C7E
0x180014c68  mov     rax, [rcx]
0x180014c6b  xor     r9d, r9d
0x180014c6e  mov     r8, rdi
0x180014c71  mov     rax, [rax+18h]
0x180014c75  lea     edx, [r9+3]
0x180014c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c7e  mov     rcx, r12; lpCriticalSection
0x180014c81  call    cs:__imp_LeaveCriticalSection
0x180014c87  mov     eax, edi
0x180014c89  mov     rcx, [rbp+var_10]
0x180014c8d  xor     rcx, rsp; StackCookie
0x180014c90  call    __security_check_cookie
0x180014c95  lea     r11, [rsp+50h+var_s0]
0x180014c9a  mov     rbx, [r11+40h]
0x180014c9e  mov     rsi, [r11+48h]
0x180014ca2  mov     rsp, r11
0x180014ca5  pop     r15
0x180014ca7  pop     r14
0x180014ca9  pop     r12
0x180014cab  pop     rdi
0x180014cac  pop     rbp
0x180014cad  retn
```
