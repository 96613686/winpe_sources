# Microsoft::HostGuardian::Client::Plugin::AttestationHandler::RequestCAIntermediateCertificate(HgBlob * const,HgBlob * const,HgBlob * const,HgBlob * const,ShsAttestationFlag &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,uint *,AttestationResult * *)

- ea: `0x180008ecc`
- end: `0x180009038`
- name: `?RequestCAIntermediateCertificate@AttestationHandler@Plugin@Client@HostGuardian@Microsoft@@QEAA?AW4AttestationError@@QEAUHgBlob@@000AEAW4ShsAttestationFlag@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAIPEAPEAUAttestationResult@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, __int64, __int64, _DWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007f80`

## callees

- `0x180001520`
- `0x180005e18`
- `0x180006260`
- `0x180008ecc`

## import_xrefs

- `hgattest!IssueCAIntermediateCertificate` at `0x180008fc0`
- `hgattest!IssueCAIntermediateCertificate` at `0x180009012`
- `hgattest!IssueCAIntermediateCertificate` at `0x180008fc0`
- `hgattest!IssueCAIntermediateCertificate` at `0x180009012`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Plugin::AttestationHandler::RequestCAIntermediateCertificate(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _DWORD *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v11; // rdx
  _DWORD *v15; // rcx
  __int128 *v16; // rax
  unsigned int v17; // ebx
  int v18; // [rsp+40h] [rbp-71h] BYREF
  __int128 v19; // [rsp+48h] [rbp-69h] BYREF
  __int128 v20; // [rsp+58h] [rbp-59h]
  __int128 v21; // [rsp+68h] [rbp-49h]
  __int128 v22; // [rsp+78h] [rbp-39h] BYREF
  __int128 v23; // [rsp+88h] [rbp-29h]
  __int64 v24; // [rsp+98h] [rbp-19h]

  v11 = *a1;
  v19 = 0;
  v18 = 3;
  v20 = 0;
  v21 = 0;
  if ( *(_DWORD *)(v11 + 112) == 1 )
  {
    *a6 = 0;
    v22 = 0;
    v24 = 0;
    v23 = 0;
    LODWORD(v22) = 40;
    return ((__int64 (__fastcall *)(__int64, __int128 *, __int64, __int64, __int64, __int64, __int64, __int64, int, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))IssueCAIntermediateCertificate)(
             1,
             &v22,
             a2,
             a3,
             a4,
             a5,
             a8,
             a9,
             v18,
             v19,
             *((_QWORD *)&v19 + 1),
             v20,
             *((_QWORD *)&v20 + 1),
             v21,
             *((_QWORD *)&v21 + 1));
  }
  else if ( *(_DWORD *)(v11 + 112) == 2 )
  {
    std::wstring::wstring((__int64)&v22, v11);
    v15 = (_DWORD *)*a1;
    HIDWORD(v19) = v23;
    v16 = &v22;
    if ( *((_QWORD *)&v23 + 1) > 7u )
      v16 = (__int128 *)v22;
    *(_QWORD *)&v20 = v16;
    DWORD2(v19) = v15[29];
    HIDWORD(v20) = v15[30];
    DWORD2(v20) = v15[31];
    *((_QWORD *)&v21 + 1) = &v18;
    LODWORD(v21) = 1;
    v17 = ((__int64 (__fastcall *)(__int64, __int128 *, __int64, __int64, __int64, __int64, __int64, __int64, int, __int64, _QWORD, __int128 *, _QWORD, _QWORD))IssueCAIntermediateCertificate)(
            2,
            &v19,
            a2,
            a3,
            a4,
            a5,
            a8,
            a9,
            v18,
            0x100000030LL,
            *((_QWORD *)&v19 + 1),
            v16,
            *((_QWORD *)&v20 + 1),
            v21);
    std::wstring::~wstring((char **)&v22);
    return v17;
  }
  else
  {
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x180008ecc  push    rbp
0x180008ece  push    rbx
0x180008ecf  push    rsi
0x180008ed0  push    rdi
0x180008ed1  push    r12
0x180008ed3  push    r13
0x180008ed5  push    r14
0x180008ed7  push    r15
0x180008ed9  lea     rbp, [rsp-7]
0x180008ede  sub     rsp, 0B8h
0x180008ee5  mov     rax, cs:__security_cookie
0x180008eec  xor     rax, rsp
0x180008eef  mov     [rbp+3Fh+var_50], rax
0x180008ef3  mov     r14, [rbp+3Fh+arg_20]
0x180008ef7  xorps   xmm0, xmm0
0x180008efa  mov     r15, [rbp+3Fh+arg_38]
0x180008f01  mov     r13, rcx
0x180008f04  mov     r12, [rbp+3Fh+arg_40]
0x180008f0b  mov     rbx, rdx
0x180008f0e  mov     rdx, [rcx]
0x180008f11  mov     rdi, r8
0x180008f14  mov     r8, [rbp+3Fh+arg_28]
0x180008f18  mov     rsi, r9
0x180008f1b  movups  [rbp+3Fh+var_A8], xmm0
0x180008f1f  mov     [rbp+3Fh+var_B0], 3
0x180008f26  movups  [rbp+3Fh+var_98], xmm0
0x180008f2a  movups  [rbp+3Fh+var_88], xmm0
0x180008f2e  mov     ecx, [rdx+70h]
0x180008f31  sub     ecx, 1
0x180008f34  jz      loc_180008FD5
0x180008f3a  cmp     ecx, 1
0x180008f3d  jz      short loc_180008F49
0x180008f3f  mov     eax, 80004001h
0x180008f44  jmp     loc_180009018
0x180008f49  lea     rcx, [rbp+3Fh+var_78]
0x180008f4d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180008f52  mov     rcx, [r13+0]
0x180008f56  lea     rdx, [rbp+3Fh+var_A8]
0x180008f5a  mov     eax, dword ptr [rbp+3Fh+var_68]
0x180008f5d  mov     r9, rdi
0x180008f60  cmp     qword ptr [rbp+3Fh+var_68+8], 7
0x180008f65  mov     r8, rbx
0x180008f68  mov     dword ptr [rbp+3Fh+var_A8+0Ch], eax
0x180008f6b  lea     rax, [rbp+3Fh+var_78]
0x180008f6f  cmova   rax, qword ptr [rbp+3Fh+var_78]
0x180008f74  mov     qword ptr [rbp+3Fh+var_98], rax
0x180008f78  mov     dword ptr [rbp+3Fh+var_A8+4], 1
0x180008f7f  mov     eax, [rcx+74h]
0x180008f82  mov     dword ptr [rbp+3Fh+var_A8+8], eax
0x180008f85  mov     eax, [rcx+78h]
0x180008f88  mov     dword ptr [rbp+3Fh+var_98+0Ch], eax
0x180008f8b  mov     eax, [rcx+7Ch]
0x180008f8e  mov     ecx, 2
0x180008f93  mov     [rsp+0F0h+var_B8], r12
0x180008f98  mov     dword ptr [rbp+3Fh+var_98+8], eax
0x180008f9b  lea     rax, [rbp+3Fh+var_B0]
0x180008f9f  mov     [rsp+0F0h+var_C0], r15
0x180008fa4  mov     [rsp+0F0h+var_C8], r14
0x180008fa9  mov     qword ptr [rbp+3Fh+var_88+8], rax
0x180008fad  mov     dword ptr [rbp+3Fh+var_88], 1
0x180008fb4  mov     dword ptr [rbp+3Fh+var_A8], 30h ; '0'
0x180008fbb  mov     [rsp+0F0h+var_D0], rsi
0x180008fc0  call    cs:__imp_IssueCAIntermediateCertificate
0x180008fc6  lea     rcx, [rbp+3Fh+var_78]
0x180008fca  mov     ebx, eax
0x180008fcc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008fd1  mov     eax, ebx
0x180008fd3  jmp     short loc_180009018
0x180008fd5  xor     eax, eax
0x180008fd7  mov     [rsp+0F0h+var_B8], r12
0x180008fdc  mov     dword ptr [r8], 0
0x180008fe3  lea     rdx, [rbp+3Fh+var_78]
0x180008fe7  mov     [rsp+0F0h+var_C0], r15
0x180008fec  mov     r9, rdi
0x180008fef  movups  [rbp+3Fh+var_78], xmm0
0x180008ff3  lea     ecx, [rax+1]
0x180008ff6  mov     [rsp+0F0h+var_C8], r14
0x180008ffb  mov     r8, rbx
0x180008ffe  mov     [rbp+3Fh+var_58], rax
0x180009002  movups  [rbp+3Fh+var_68], xmm0
0x180009006  mov     dword ptr [rbp+3Fh+var_78], 28h ; '('
0x18000900d  mov     [rsp+0F0h+var_D0], rsi
0x180009012  call    cs:__imp_IssueCAIntermediateCertificate
0x180009018  mov     rcx, [rbp+3Fh+var_50]
0x18000901c  xor     rcx, rsp; StackCookie
0x18000901f  call    __security_check_cookie
0x180009024  add     rsp, 0B8h
0x18000902b  pop     r15
0x18000902d  pop     r14
0x18000902f  pop     r13
0x180009031  pop     r12
0x180009033  pop     rdi
0x180009034  pop     rsi
0x180009035  pop     rbx
0x180009036  pop     rbp
0x180009037  retn
```
