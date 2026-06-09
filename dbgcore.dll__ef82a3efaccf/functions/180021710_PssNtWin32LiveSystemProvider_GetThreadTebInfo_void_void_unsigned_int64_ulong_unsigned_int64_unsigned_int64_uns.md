# PssNtWin32LiveSystemProvider::GetThreadTebInfo(void *,void *,unsigned __int64 *,ulong *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,bool)

- ea: `0x180021710`
- end: `0x180021944`
- name: `?GetThreadTebInfo@PssNtWin32LiveSystemProvider@@UEAAJPEAX0PEA_KPEAK111111_N@Z`
- size: `564`
- prototype: `__int64 __usercall@<rax>(PssNtWin32LiveSystemProvider *__hidden this@<rcx>, void *@<rdx>, void *@<r8>, unsigned __int64 *@<r9>, unsigned int *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, bool)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001710`
- `0x1800021f4`
- `0x18001601c`
- `0x180021710`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall PssNtWin32LiveSystemProvider::GetThreadTebInfo(
        PssNtWin32LiveSystemProvider *this,
        void *a2,
        void *a3,
        unsigned __int64 *a4,
        unsigned int *a5,
        unsigned __int64 *a6,
        unsigned __int64 *a7,
        unsigned __int64 *a8,
        unsigned __int64 *a9,
        unsigned __int64 *a10,
        unsigned __int64 *a11,
        bool a12)
{
  char v15; // r14
  __int64 result; // rax
  unsigned int ThreadTebInfo; // ecx
  unsigned __int64 v18; // r8
  __int64 (__fastcall **v19)(PssNtWin32LiveSystemProvider *, void *, unsigned __int64, unsigned int **, int); // rax
  void *v20; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v21; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 *v22; // [rsp+60h] [rbp-A0h]
  unsigned __int64 *v23; // [rsp+68h] [rbp-98h]
  unsigned __int64 *v24; // [rsp+70h] [rbp-90h]
  unsigned __int64 *v25; // [rsp+78h] [rbp-88h]
  _BYTE v26[704]; // [rsp+80h] [rbp-80h] BYREF

  v21 = a5;
  v25 = a8;
  v24 = a9;
  v23 = a10;
  v20 = a3;
  v22 = a11;
  memset_0(v26, 0, sizeof(v26));
  if ( (*((unsigned int (__fastcall **)(_QWORD, _QWORD, _BYTE *, __int64))this + 142))(
         *((_QWORD *)this + 153),
         0,
         v26,
         704)
    || (v26[36] & 2) == 0 )
  {
    v15 = 0;
    if ( a12 )
      return 2147500037LL;
  }
  else
  {
    v15 = 1;
  }
  result = (*(__int64 (__fastcall **)(PssNtWin32LiveSystemProvider *, void *, unsigned __int64 *, unsigned int *))(*(_QWORD *)this + 192LL))(
             this,
             v20,
             a4,
             v21);
  if ( !(_DWORD)result )
  {
    ThreadTebInfo = Win32LiveSystemProvider::TibGetThreadTebInfo(this, a2, *a4, a6, a7, v25, v24, v23, v22);
    if ( !ThreadTebInfo && v15 && a12 )
    {
      v18 = *a4;
      LODWORD(v20) = 0;
      v19 = *(__int64 (__fastcall ***)(PssNtWin32LiveSystemProvider *, void *, unsigned __int64, unsigned int **, int))this;
      v21 = 0;
      ThreadTebInfo = v19[30](this, a2, v18, &v21, 8);
      if ( !ThreadTebInfo )
      {
        if ( !(*(unsigned int (__fastcall **)(PssNtWin32LiveSystemProvider *, void *, unsigned int *, void **, int))(*(_QWORD *)this + 240LL))(
                this,
                a2,
                v21 + 1,
                &v20,
                4) )
          *a6 = (unsigned int)v20;
        ThreadTebInfo = (*(__int64 (__fastcall **)(PssNtWin32LiveSystemProvider *, void *, unsigned int *, void **, int))(*(_QWORD *)this + 240LL))(
                          this,
                          a2,
                          v21 + 2,
                          &v20,
                          4);
        if ( !ThreadTebInfo )
          *a7 = (unsigned int)v20;
      }
      *a4 = (unsigned __int64)v21;
    }
    return ThreadTebInfo;
  }
  return result;
}

```

## disassembly

```asm
0x180021710  push    rbp
0x180021712  push    rbx
0x180021713  push    rsi
0x180021714  push    rdi
0x180021715  push    r12
0x180021717  push    r13
0x180021719  push    r14
0x18002171b  lea     rbp, [rsp-250h]
0x180021723  sub     rsp, 350h
0x18002172a  mov     rax, cs:__security_cookie
0x180021731  xor     rax, rsp
0x180021734  mov     [rbp+280h+var_40], rax
0x18002173b  mov     rax, [rbp+280h+arg_20]
0x180021742  mov     rsi, rdx
0x180021745  mov     r13, [rbp+280h+arg_28]
0x18002174c  mov     rbx, rcx
0x18002174f  mov     r12, [rbp+280h+arg_30]
0x180021756  lea     rcx, [rbp+280h+var_300]; void *
0x18002175a  mov     [rsp+380h+var_328], rax
0x18002175f  mov     r14d, 2C0h
0x180021765  mov     rax, [rbp+280h+arg_38]
0x18002176c  xor     edx, edx; Val
0x18002176e  mov     [rsp+380h+var_308], rax
0x180021773  mov     rdi, r9
0x180021776  mov     rax, [rbp+280h+arg_40]
0x18002177d  mov     [rsp+380h+var_310], rax
0x180021782  mov     rax, [rbp+280h+arg_48]
0x180021789  mov     [rsp+380h+var_318], rax
0x18002178e  mov     rax, [rbp+280h+arg_50]
0x180021795  mov     [rsp+380h+var_330], r8
0x18002179a  mov     r8d, r14d; Size
0x18002179d  mov     [rsp+380h+var_320], rax
0x1800217a2  call    memset_0
0x1800217a7  mov     rcx, [rbx+4C8h]
0x1800217ae  lea     r8, [rbp+280h+var_300]
0x1800217b2  mov     rax, [rbx+470h]
0x1800217b9  mov     r9d, r14d
0x1800217bc  xor     edx, edx
0x1800217be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217c3  test    eax, eax
0x1800217c5  jnz     loc_18002192D
0x1800217cb  test    [rbp+280h+var_2DC], 2
0x1800217cf  jz      loc_18002192D
0x1800217d5  mov     r14b, 1
0x1800217d8  mov     rax, [rbx]
0x1800217db  mov     r8, rdi
0x1800217de  mov     r9, [rsp+380h+var_328]
0x1800217e3  mov     rcx, rbx
0x1800217e6  mov     rdx, [rsp+380h+var_330]
0x1800217eb  mov     rax, [rax+0C0h]
0x1800217f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217f7  test    eax, eax
0x1800217f9  jnz     loc_18002190C
0x1800217ff  mov     rax, [rsp+380h+var_320]
0x180021804  mov     r9, r13; unsigned __int64 *
0x180021807  mov     r8, [rdi]; unsigned __int64
0x18002180a  mov     rdx, rsi; void *
0x18002180d  mov     [rsp+380h+var_340], rax; unsigned __int64 *
0x180021812  mov     rcx, rbx; this
0x180021815  mov     rax, [rsp+380h+var_318]
0x18002181a  mov     [rsp+380h+var_348], rax; unsigned __int64 *
0x18002181f  mov     rax, [rsp+380h+var_310]
0x180021824  mov     [rsp+380h+var_350], rax; unsigned __int64 *
0x180021829  mov     rax, [rsp+380h+var_308]
0x18002182e  mov     [rsp+380h+var_358], rax; unsigned __int64 *
0x180021833  mov     [rsp+380h+var_360], r12; unsigned __int64 *
0x180021838  call    ?TibGetThreadTebInfo@Win32LiveSystemProvider@@IEAAJPEAX_KPEA_K22222@Z; Win32LiveSystemProvider::TibGetThreadTebInfo(void *,unsigned __int64,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x18002183d  mov     ecx, eax
0x18002183f  test    eax, eax
0x180021841  jnz     loc_18002190A
0x180021847  test    r14b, r14b
0x18002184a  jz      loc_18002190A
0x180021850  cmp     [rbp+280h+arg_58], al
0x180021856  jz      loc_18002190A
0x18002185c  mov     r8, [rdi]
0x18002185f  lea     r9, [rsp+380h+var_328]
0x180021864  mov     dword ptr [rsp+380h+var_330], eax
0x180021868  mov     rdx, rsi
0x18002186b  mov     rax, [rbx]
0x18002186e  mov     rcx, rbx
0x180021871  mov     [rsp+380h+var_328], 0
0x18002187a  mov     dword ptr [rsp+380h+var_360], 8
0x180021882  mov     rax, [rax+0F0h]
0x180021889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002188e  mov     ecx, eax
0x180021890  test    eax, eax
0x180021892  jnz     short loc_180021902
0x180021894  mov     rax, [rbx]
0x180021897  lea     r14d, [rcx+4]
0x18002189b  mov     r8, [rsp+380h+var_328]
0x1800218a0  lea     r9, [rsp+380h+var_330]
0x1800218a5  add     r8, 4
0x1800218a9  mov     dword ptr [rsp+380h+var_360], r14d
0x1800218ae  mov     rdx, rsi
0x1800218b1  mov     rcx, rbx
0x1800218b4  mov     rax, [rax+0F0h]
0x1800218bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218c0  test    eax, eax
0x1800218c2  jnz     short loc_1800218CC
0x1800218c4  mov     eax, dword ptr [rsp+380h+var_330]
0x1800218c8  mov     [r13+0], rax
0x1800218cc  mov     rax, [rbx]
0x1800218cf  lea     r9, [rsp+380h+var_330]
0x1800218d4  mov     r8, [rsp+380h+var_328]
0x1800218d9  mov     rdx, rsi
0x1800218dc  add     r8, 8
0x1800218e0  mov     dword ptr [rsp+380h+var_360], r14d
0x1800218e5  mov     rcx, rbx
0x1800218e8  mov     rax, [rax+0F0h]
0x1800218ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218f4  mov     ecx, eax
0x1800218f6  test    eax, eax
0x1800218f8  jnz     short loc_180021902
0x1800218fa  mov     eax, dword ptr [rsp+380h+var_330]
0x1800218fe  mov     [r12], rax
0x180021902  mov     rax, [rsp+380h+var_328]
0x180021907  mov     [rdi], rax
0x18002190a  mov     eax, ecx
0x18002190c  mov     rcx, [rbp+280h+var_40]
0x180021913  xor     rcx, rsp; StackCookie
0x180021916  call    __security_check_cookie
0x18002191b  add     rsp, 350h
0x180021922  pop     r14
0x180021924  pop     r13
0x180021926  pop     r12
0x180021928  pop     rdi
0x180021929  pop     rsi
0x18002192a  pop     rbx
0x18002192b  pop     rbp
0x18002192c  retn
0x18002192d  xor     r14b, r14b
0x180021930  cmp     [rbp+280h+arg_58], r14b
0x180021937  jz      loc_1800217D8
0x18002193d  mov     eax, 80004005h
0x180021942  jmp     short loc_18002190C
```
