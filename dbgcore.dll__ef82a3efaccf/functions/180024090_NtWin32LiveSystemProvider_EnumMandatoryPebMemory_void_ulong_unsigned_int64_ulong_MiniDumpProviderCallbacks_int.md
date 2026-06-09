# NtWin32LiveSystemProvider::EnumMandatoryPebMemory(void *,ulong,unsigned __int64,ulong,MiniDumpProviderCallbacks *,int)

- ea: `0x180024090`
- end: `0x180024239`
- name: `?EnumMandatoryPebMemory@NtWin32LiveSystemProvider@@UEAAJPEAXK_KKPEAVMiniDumpProviderCallbacks@@H@Z`
- size: `425`
- prototype: `__int64 __fastcall(NtWin32LiveSystemProvider *__hidden this, void *, unsigned int, unsigned __int64, unsigned int, struct MiniDumpProviderCallbacks *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180024090`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall NtWin32LiveSystemProvider::EnumMandatoryPebMemory(
        NtWin32LiveSystemProvider *this,
        void *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        struct MiniDumpProviderCallbacks *a6,
        int a7)
{
  unsigned int v9; // edi
  __int64 result; // rax
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // r15
  unsigned __int64 v14; // rsi
  __int64 v15; // rax
  int (__fastcall *v16)(NtWin32LiveSystemProvider *, void *, unsigned __int64, __int128 *); // rax
  __int64 v17; // rdi
  unsigned __int64 v18; // rbx
  __int128 v20; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v21; // [rsp+48h] [rbp-B8h]
  __int128 v22; // [rsp+58h] [rbp-A8h]
  _BYTE v23[872]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v24; // [rsp+3D8h] [rbp+2D8h]

  v9 = 2000;
  memset_0(v23, 0, 0x7D0u);
  if ( a5 <= 0x7D0 )
    v9 = a5;
  result = (*(__int64 (__fastcall **)(NtWin32LiveSystemProvider *, void *, __int64, _BYTE *, unsigned int))(*(_QWORD *)this + 240LL))(
             this,
             a2,
             a4,
             v23,
             v9);
  if ( !(_DWORD)result )
  {
    if ( a7 )
    {
      if ( v9 >= 0x370 )
      {
        v12 = v24;
        v13 = v24 + 0x100000000LL;
        v14 = v24;
        if ( v24 < v24 + 0x100000000LL )
        {
          while ( 1 )
          {
            v15 = *(_QWORD *)this;
            v20 = 0;
            v16 = *(int (__fastcall **)(NtWin32LiveSystemProvider *, void *, unsigned __int64, __int128 *))(v15 + 248);
            v21 = 0;
            v22 = 0;
            if ( v16(this, a2, v14, &v20) < 0 )
              return 0;
            if ( (v22 & 0x1000) == 0 )
            {
              v14 = v20 + *((_QWORD *)&v21 + 1);
              goto LABEL_19;
            }
            v17 = v20;
            v18 = *((_QWORD *)&v21 + 1);
            if ( (unsigned __int64)v20 < v14 )
              v18 = v20 - v12 + *((_QWORD *)&v21 + 1);
            if ( v18 + (unsigned __int64)v20 > v13 )
              v18 = v12 - v20 + 0x100000000LL;
            if ( v18 > 0xFFFFFFFF )
              break;
            if ( v18 )
              goto LABEL_16;
LABEL_17:
            v14 = v18 + v17;
LABEL_19:
            if ( v14 > v13 )
              return 0;
          }
          v18 = 0xFFFFFFFFLL;
LABEL_16:
          (**(void (__fastcall ***)(struct MiniDumpProviderCallbacks *, _QWORD, _QWORD))a6)(a6, v20, (unsigned int)v18);
          goto LABEL_17;
        }
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180024090  mov     [rsp-8+arg_10], rbx
0x180024095  push    rbp
0x180024096  push    rsi
0x180024097  push    rdi
0x180024098  push    r12
0x18002409a  push    r13
0x18002409c  push    r14
0x18002409e  push    r15
0x1800240a0  lea     rbp, [rsp-750h]
0x1800240a8  sub     rsp, 850h
0x1800240af  mov     rax, cs:__security_cookie
0x1800240b6  xor     rax, rsp
0x1800240b9  mov     [rbp+780h+var_40], rax
0x1800240c0  mov     r13, [rbp+780h+arg_28]
0x1800240c7  mov     rsi, rdx
0x1800240ca  mov     [rsp+880h+var_850], rdx
0x1800240cf  mov     r12, rcx
0x1800240d2  mov     edi, 7D0h
0x1800240d7  lea     rcx, [rsp+880h+var_810]; void *
0x1800240dc  mov     r8d, edi; Size
0x1800240df  xor     edx, edx; Val
0x1800240e1  mov     rbx, r9
0x1800240e4  call    memset_0
0x1800240e9  mov     rax, [r12]
0x1800240ed  lea     r9, [rsp+880h+var_810]
0x1800240f2  cmp     [rbp+780h+arg_20], edi
0x1800240f8  mov     r8, rbx
0x1800240fb  mov     rdx, rsi
0x1800240fe  mov     rcx, r12
0x180024101  cmovbe  edi, [rbp+780h+arg_20]
0x180024108  mov     rax, [rax+0F0h]
0x18002410f  mov     [rsp+880h+var_860], edi
0x180024113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024118  test    eax, eax
0x18002411a  jnz     loc_18002420F
0x180024120  cmp     [rbp+780h+arg_30], eax
0x180024126  jz      loc_18002420D
0x18002412c  cmp     edi, 370h
0x180024132  jb      loc_18002420D
0x180024138  mov     r14, [rbp+780h+var_4A8]
0x18002413f  mov     r15, 100000000h
0x180024149  add     r15, r14
0x18002414c  mov     rsi, r14
0x18002414f  cmp     r14, r15
0x180024152  ja      loc_18002420D
0x180024158  mov     rax, [r12]
0x18002415c  lea     r9, [rsp+880h+var_848]
0x180024161  mov     rdx, [rsp+880h+var_850]
0x180024166  xorps   xmm0, xmm0
0x180024169  mov     r8, rsi
0x18002416c  mov     rcx, r12
0x18002416f  movups  [rsp+880h+var_848], xmm0
0x180024174  mov     rax, [rax+0F8h]
0x18002417b  movups  [rsp+880h+var_838], xmm0
0x180024180  movups  [rsp+880h+var_828], xmm0
0x180024185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002418a  test    eax, eax
0x18002418c  js      short loc_18002420D
0x18002418e  test    dword ptr [rsp+880h+var_828], 1000h
0x180024196  jz      short loc_1800241FA
0x180024198  mov     rdi, qword ptr [rsp+880h+var_848]
0x18002419d  mov     rbx, qword ptr [rsp+880h+var_838+8]
0x1800241a2  cmp     rdi, rsi
0x1800241a5  jnb     short loc_1800241B0
0x1800241a7  mov     rax, rdi
0x1800241aa  sub     rax, r14
0x1800241ad  add     rbx, rax
0x1800241b0  lea     rax, [rbx+rdi]
0x1800241b4  cmp     rax, r15
0x1800241b7  jbe     short loc_1800241CC
0x1800241b9  mov     rbx, r14
0x1800241bc  mov     rax, 100000000h
0x1800241c6  sub     rbx, rdi
0x1800241c9  add     rbx, rax
0x1800241cc  mov     eax, 0FFFFFFFFh
0x1800241d1  cmp     rbx, rax
0x1800241d4  jbe     short loc_1800241DA
0x1800241d6  mov     ebx, eax
0x1800241d8  jmp     short loc_1800241DF
0x1800241da  test    rbx, rbx
0x1800241dd  jz      short loc_1800241F4
0x1800241df  mov     rax, [r13+0]
0x1800241e3  mov     r8d, ebx
0x1800241e6  mov     rdx, rdi
0x1800241e9  mov     rcx, r13
0x1800241ec  mov     rax, [rax]
0x1800241ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241f4  lea     rsi, [rbx+rdi]
0x1800241f8  jmp     short loc_180024204
0x1800241fa  mov     rsi, qword ptr [rsp+880h+var_838+8]
0x1800241ff  add     rsi, qword ptr [rsp+880h+var_848]
0x180024204  cmp     rsi, r15
0x180024207  jbe     loc_180024158
0x18002420d  xor     eax, eax
0x18002420f  mov     rcx, [rbp+780h+var_40]
0x180024216  xor     rcx, rsp; StackCookie
0x180024219  call    __security_check_cookie
0x18002421e  mov     rbx, [rsp+880h+arg_10]
0x180024226  add     rsp, 850h
0x18002422d  pop     r15
0x18002422f  pop     r14
0x180024231  pop     r13
0x180024233  pop     r12
0x180024235  pop     rdi
0x180024236  pop     rsi
0x180024237  pop     rbp
0x180024238  retn
```
