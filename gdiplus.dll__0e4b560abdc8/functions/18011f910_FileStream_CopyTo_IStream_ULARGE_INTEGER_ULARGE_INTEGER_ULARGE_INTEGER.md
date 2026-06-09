# FileStream::CopyTo(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x18011f910`
- end: `0x18011fe9f`
- name: `?CopyTo@FileStream@@UEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2@Z`
- size: `1423`
- prototype: `__int64 __fastcall(FileStream *__hidden this, struct IStream *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800e9380`
- `0x1800ea0ec`
- `0x18011f910`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011f99f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011f99f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011fe6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011fe6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18011fb22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18011fb22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011fe57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011fe57`

## pseudocode

```c
__int64 __fastcall FileStream::CopyTo(
        FileStream *this,
        struct IStream *a2,
        union _ULARGE_INTEGER a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5)
{
  ULONGLONG v8; // r15
  ULONGLONG v9; // r14
  int v10; // r12d
  DWORD LowPart; // r13d
  __int64 v12; // rsi
  __int64 v13; // rdi
  unsigned __int64 v14; // rdx
  void *v15; // rcx
  int v16; // edx
  struct IStream *v17; // rsi
  FileStream *v18; // rdi
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 (__fastcall *v21)(FileStream *, __int64, __int64); // rax
  __int64 v22; // rax
  __int64 (__fastcall *v23)(FileStream *, unsigned __int64, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v24)(struct IStream *, unsigned __int64, _QWORD, _QWORD); // rax
  void *pv; // [rsp+30h] [rbp-D0h]
  unsigned int v27; // [rsp+44h] [rbp-BCh]
  int v28; // [rsp+48h] [rbp-B8h]
  unsigned int v30; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v31; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v34; // [rsp+70h] [rbp-90h]
  ULONGLONG v35; // [rsp+78h] [rbp-88h]
  ULONGLONG v36; // [rsp+80h] [rbp-80h]
  __int64 v37; // [rsp+88h] [rbp-78h]
  __int64 v38; // [rsp+90h] [rbp-70h]
  __int64 v39; // [rsp+98h] [rbp-68h]
  __int64 v40; // [rsp+A0h] [rbp-60h]
  union _ULARGE_INTEGER *v41; // [rsp+A8h] [rbp-58h]
  union _ULARGE_INTEGER *v42; // [rsp+B0h] [rbp-50h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B8h] [rbp-48h]
  _BYTE v44[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v45; // [rsp+D0h] [rbp-30h]

  v34 = (unsigned __int64)this;
  v41 = a4;
  v42 = a5;
  v30 = 0;
  v31 = 0;
  v8 = 0;
  v35 = 0;
  v9 = 0;
  v36 = 0;
  v32 = 0;
  v33 = 0;
  memset_0(v44, 0, 0x50u);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((_QWORD *)this + 9) == -1 )
  {
    v10 = -2147286782;
    goto LABEL_51;
  }
  if ( !a2 )
  {
    v10 = -2147286953;
    goto LABEL_51;
  }
  LowPart = a3.LowPart;
  if ( a3.QuadPart > 0x2000 )
    LowPart = 0x2000;
  v10 = (*(__int64 (__fastcall **)(FileStream *, _QWORD, __int64, unsigned __int64 *))(*(_QWORD *)this + 40LL))(
          this,
          0,
          1,
          &v32);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, unsigned __int64 *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            1,
            &v33);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(FileStream *, _BYTE *, __int64))(*(_QWORD *)this + 96LL))(this, v44, 1);
      if ( v10 >= 0 )
      {
        v12 = v45;
        v27 = HIDWORD(v45);
        v10 = (*(__int64 (__fastcall **)(struct IStream *, _BYTE *, __int64))(*(_QWORD *)a2 + 96LL))(a2, v44, 1);
        if ( v10 >= 0 )
        {
          v13 = v45;
          if ( __SPAIR64__(v27, v12) < 0 || v45 < 0 )
          {
            v10 = -2147286789;
            goto LABEL_51;
          }
          v14 = v12 - v32;
          if ( a3.QuadPart > v12 - v32 )
            a3.QuadPart = v12 - v32;
          if ( v14 <= v45 - v33
            || (v13 = v14 + v33,
                v10 = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int64))(*(_QWORD *)a2 + 48LL))(
                        a2,
                        v14 + v33),
                v10 >= 0) )
          {
            pv = CoTaskMemAlloc(LowPart);
            v15 = pv;
            if ( !pv )
            {
              v10 = -2147287032;
              goto LABEL_51;
            }
            v16 = 1;
            v28 = 1;
            if ( v32 >= v33 )
            {
              v17 = a2;
            }
            else
            {
              v28 = 0;
              v10 = (*(__int64 (__fastcall **)(unsigned __int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v34 + 40LL))(
                      v34,
                      v12 - LowPart,
                      0,
                      0);
              if ( v10 < 0
                || (v17 = a2,
                    v10 = (*(__int64 (__fastcall **)(struct IStream *, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(
                            a2,
                            v13 - LowPart,
                            0,
                            0),
                    v10 < 0) )
              {
LABEL_49:
                CoTaskMemFree(pv);
                goto LABEL_51;
              }
              v15 = pv;
              v16 = 0;
            }
            v18 = (FileStream *)v34;
            if ( a3.QuadPart <= LowPart )
              LowPart = a3.LowPart;
            while ( a3.QuadPart )
            {
              v10 = (*(__int64 (__fastcall **)(FileStream *, void *, _QWORD, unsigned int *))(*(_QWORD *)v18 + 24LL))(
                      v18,
                      v15,
                      LowPart,
                      &v30);
              if ( v10 < 0 )
                goto LABEL_49;
              if ( v30 != LowPart )
              {
                v10 = -2147287010;
                goto LABEL_49;
              }
              v34 = v30;
              v19 = *(_QWORD *)v17;
              v8 += v30;
              v35 = v8;
              v10 = (*(__int64 (__fastcall **)(struct IStream *, void *, _QWORD, unsigned int *))(v19 + 32))(
                      v17,
                      pv,
                      LowPart,
                      &v31);
              if ( v10 < 0 )
                goto LABEL_49;
              if ( v31 != LowPart )
              {
                v10 = -2147287011;
                goto LABEL_49;
              }
              v16 = v28;
              a3.QuadPart -= LowPart;
              v37 = LowPart;
              v9 += v31;
              v36 = v9;
              if ( a3.QuadPart <= LowPart )
                LowPart = a3.LowPart;
              if ( !v28 && a3.QuadPart )
              {
                v20 = *(_QWORD *)v18;
                v38 = LowPart + 0x2000;
                v21 = *(__int64 (__fastcall **)(FileStream *, __int64, __int64))(v20 + 40);
                v39 = -v38;
                v10 = v21(v18, -v38, 1);
                if ( v10 < 0 )
                  goto LABEL_49;
                v22 = *(_QWORD *)v17;
                v40 = LowPart + 0x2000;
                v10 = (*(__int64 (__fastcall **)(struct IStream *, __int64, __int64))(v22 + 40))(v17, -v40, 1);
                if ( v10 < 0 )
                  goto LABEL_49;
                v16 = v28;
              }
              v15 = pv;
            }
            if ( v16
              || (v23 = *(__int64 (__fastcall **)(FileStream *, unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)v18 + 40LL),
                  v32 += v8,
                  v10 = v23(v18, v32, 0, 0),
                  v10 >= 0)
              && (v24 = *(__int64 (__fastcall **)(struct IStream *, unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)v17 + 40LL),
                  v33 += v9,
                  v10 = v24(v17, v33, 0, 0),
                  v10 >= 0) )
            {
              if ( v41 )
              {
                LODWORD(v35) = v8;
                v41->QuadPart = v35;
              }
              if ( v42 )
              {
                LODWORD(v36) = v9;
                v42->QuadPart = v36;
              }
            }
            goto LABEL_49;
          }
        }
      }
    }
  }
LABEL_51:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18011f910  push    rbp
0x18011f912  push    rbx
0x18011f913  push    rsi
0x18011f914  push    rdi
0x18011f915  push    r12
0x18011f917  push    r13
0x18011f919  push    r14
0x18011f91b  push    r15
0x18011f91d  lea     rbp, [rsp-28h]
0x18011f922  sub     rsp, 128h
0x18011f929  mov     rax, cs:__security_cookie
0x18011f930  xor     rax, rsp
0x18011f933  mov     [rbp+60h+var_50], rax
0x18011f937  mov     rax, [rbp+60h+arg_20]
0x18011f93e  xor     r12d, r12d
0x18011f941  mov     rbx, r8
0x18011f944  mov     [rsp+160h+var_110], rdx
0x18011f949  mov     rdi, rdx
0x18011f94c  mov     [rsp+160h+var_F0], rcx
0x18011f951  mov     rsi, rcx
0x18011f954  mov     [rbp+60h+var_B8], r9
0x18011f958  lea     r8d, [r12+50h]; Size
0x18011f95d  mov     [rbp+60h+var_B0], rax
0x18011f961  xor     edx, edx; Val
0x18011f963  mov     [rsp+160h+var_108], r12d
0x18011f968  lea     rcx, [rbp+60h+var_A0]; void *
0x18011f96c  mov     [rsp+160h+var_104], r12d
0x18011f971  mov     r15d, r12d
0x18011f974  mov     [rsp+160h+var_E8], r12
0x18011f979  mov     r14d, r12d
0x18011f97c  mov     [rbp+60h+var_E0], r12
0x18011f980  mov     [rsp+160h+var_100], r12
0x18011f985  mov     [rsp+160h+var_F8], r12
0x18011f98a  call    memset_0
0x18011f98f  lea     rax, [rsi+8]
0x18011f993  mov     [rsp+160h+var_120], rbx
0x18011f998  mov     rcx, rax; lpCriticalSection
0x18011f99b  mov     [rbp+60h+lpCriticalSection], rax
0x18011f99f  call    cs:__imp_EnterCriticalSection
0x18011f9a6  nop     dword ptr [rax+rax+00h]
0x18011f9ab  cmp     qword ptr [rsi+48h], 0FFFFFFFFFFFFFFFFh
0x18011f9b0  jnz     short loc_18011F9BD
0x18011f9b2  mov     r12d, 80030102h
0x18011f9b8  jmp     loc_18011FE6B
0x18011f9bd  test    rdi, rdi
0x18011f9c0  jnz     short loc_18011F9CD
0x18011f9c2  mov     r12d, 80030057h
0x18011f9c8  jmp     loc_18011FE6B
0x18011f9cd  mov     eax, 2000h
0x18011f9d2  mov     [rsp+160h+pv], r12
0x18011f9d7  cmp     rbx, rax
0x18011f9da  lea     r9, [rsp+160h+var_100]
0x18011f9df  mov     r13d, ebx
0x18011f9e2  mov     r8d, 1
0x18011f9e8  cmova   r13d, eax
0x18011f9ec  mov     rdx, r12
0x18011f9ef  mov     rax, [rsi]
0x18011f9f2  mov     rcx, rsi
0x18011f9f5  mov     rax, [rax+28h]
0x18011f9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f9fe  mov     r12d, eax
0x18011fa01  test    eax, eax
0x18011fa03  js      loc_18011FE6B
0x18011fa09  mov     rax, [rdi]
0x18011fa0c  lea     r9, [rsp+160h+var_F8]
0x18011fa11  and     dword ptr [rsp+160h+pv+4], r14d
0x18011fa16  mov     r8d, 1
0x18011fa1c  and     dword ptr [rsp+160h+pv], r14d
0x18011fa21  mov     rcx, rdi
0x18011fa24  mov     rdx, [rsp+160h+pv]
0x18011fa29  mov     rax, [rax+28h]
0x18011fa2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fa32  mov     r12d, eax
0x18011fa35  test    eax, eax
0x18011fa37  js      loc_18011FE6B
0x18011fa3d  mov     rax, [rsi]
0x18011fa40  lea     rdx, [rbp+60h+var_A0]
0x18011fa44  mov     r8d, 1
0x18011fa4a  mov     rcx, rsi
0x18011fa4d  mov     rax, [rax+60h]
0x18011fa51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fa56  mov     r12d, eax
0x18011fa59  test    eax, eax
0x18011fa5b  js      loc_18011FE6B
0x18011fa61  mov     rax, [rdi]
0x18011fa64  lea     rdx, [rbp+60h+var_A0]
0x18011fa68  mov     rsi, [rbp+60h+var_90]
0x18011fa6c  mov     r8d, 1
0x18011fa72  mov     rcx, rdi
0x18011fa75  mov     [rsp+160h+var_120], rsi
0x18011fa7a  mov     rax, [rax+60h]
0x18011fa7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fa83  mov     r12d, eax
0x18011fa86  test    eax, eax
0x18011fa88  js      loc_18011FE6B
0x18011fa8e  mov     eax, dword ptr [rsp+160h+var_120+4]
0x18011fa92  mov     rdi, [rbp+60h+var_90]
0x18011fa96  mov     dword ptr [rsp+160h+pv+4], eax
0x18011fa9a  mov     dword ptr [rsp+160h+pv], esi
0x18011fa9e  cmp     [rsp+160h+pv], r14
0x18011faa3  jl      loc_18011FE65
0x18011faa9  mov     rax, rdi
0x18011faac  mov     dword ptr [rsp+160h+pv], edi
0x18011fab0  shr     rax, 20h
0x18011fab4  mov     dword ptr [rsp+160h+pv+4], eax
0x18011fab8  cmp     [rsp+160h+pv], r14
0x18011fabd  jl      loc_18011FE65
0x18011fac3  mov     rdx, rsi
0x18011fac6  sub     rdx, [rsp+160h+var_100]
0x18011facb  cmp     rbx, rdx
0x18011face  jbe     short loc_18011FAD8
0x18011fad0  mov     [rsp+160h+var_120], rbx
0x18011fad5  mov     rbx, rdx
0x18011fad8  mov     rax, [rsp+160h+var_F8]
0x18011fadd  mov     rcx, rdi
0x18011fae0  sub     rcx, rax
0x18011fae3  cmp     rdx, rcx
0x18011fae6  jbe     short loc_18011FB1F
0x18011fae8  mov     r8, [rsp+160h+var_110]
0x18011faed  lea     rdi, [rdx+rax]
0x18011faf1  mov     rcx, rdi
0x18011faf4  mov     dword ptr [rsp+160h+pv], edi
0x18011faf8  shr     rcx, 20h
0x18011fafc  mov     dword ptr [rsp+160h+pv+4], ecx
0x18011fb00  mov     rcx, r8
0x18011fb03  mov     rax, [r8]
0x18011fb06  mov     rdx, [rsp+160h+pv]
0x18011fb0b  mov     rax, [rax+30h]
0x18011fb0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fb14  mov     r12d, eax
0x18011fb17  test    eax, eax
0x18011fb19  js      loc_18011FE6B
0x18011fb1f  mov     ecx, r13d; cb
0x18011fb22  call    cs:__imp_CoTaskMemAlloc
0x18011fb29  nop     dword ptr [rax+rax+00h]
0x18011fb2e  mov     [rsp+160h+pv], rax
0x18011fb33  mov     rcx, rax
0x18011fb36  test    rax, rax
0x18011fb39  jnz     short loc_18011FB46
0x18011fb3b  mov     r12d, 80030008h
0x18011fb41  jmp     loc_18011FE6B
0x18011fb46  mov     rax, [rsp+160h+var_F8]
0x18011fb4b  mov     edx, 1
0x18011fb50  mov     [rsp+160h+var_118], edx
0x18011fb54  cmp     [rsp+160h+var_100], rax
0x18011fb59  jnb     loc_18011FC17
0x18011fb5f  and     dword ptr [rsp+160h+var_128+4], r14d
0x18011fb64  xor     r9d, r9d
0x18011fb67  mov     r10, [rsp+160h+var_F0]
0x18011fb6c  xor     r8d, r8d
0x18011fb6f  and     [rsp+160h+var_118], r14d
0x18011fb74  mov     dword ptr [rsp+160h+var_128], r13d
0x18011fb79  sub     rsi, [rsp+160h+var_128]
0x18011fb7e  mov     rax, [r10]
0x18011fb81  mov     rcx, rsi
0x18011fb84  shr     rcx, 20h
0x18011fb88  mov     dword ptr [rsp+160h+var_128+4], ecx
0x18011fb8c  mov     rcx, r10
0x18011fb8f  mov     dword ptr [rsp+160h+var_128], esi
0x18011fb93  mov     rdx, [rsp+160h+var_128]
0x18011fb98  mov     rax, [rax+28h]
0x18011fb9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fba1  mov     r12d, eax
0x18011fba4  test    eax, eax
0x18011fba6  js      loc_18011FE52
0x18011fbac  and     dword ptr [rsp+160h+var_128+4], r14d
0x18011fbb1  xor     r9d, r9d
0x18011fbb4  mov     rsi, [rsp+160h+var_110]
0x18011fbb9  xor     r8d, r8d
0x18011fbbc  mov     dword ptr [rsp+160h+var_128], r13d
0x18011fbc1  sub     rdi, [rsp+160h+var_128]
0x18011fbc6  mov     rcx, rdi
0x18011fbc9  mov     dword ptr [rsp+160h+var_128], edi
0x18011fbcd  mov     rax, [rsi]
0x18011fbd0  shr     rcx, 20h
0x18011fbd4  mov     dword ptr [rsp+160h+var_128+4], ecx
0x18011fbd8  mov     rcx, rsi
0x18011fbdb  mov     rdx, [rsp+160h+var_128]
0x18011fbe0  mov     rax, [rax+28h]
0x18011fbe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fbe9  mov     r12d, eax
0x18011fbec  test    eax, eax
0x18011fbee  js      loc_18011FE52
0x18011fbf4  mov     rcx, [rsp+160h+pv]
0x18011fbf9  mov     edx, [rsp+160h+var_118]
0x18011fbfd  and     dword ptr [rsp+160h+var_128+4], r14d
0x18011fc02  mov     rdi, [rsp+160h+var_F0]
0x18011fc07  mov     dword ptr [rsp+160h+var_128], r13d
0x18011fc0c  cmp     rbx, [rsp+160h+var_128]
0x18011fc11  cmovbe  r13d, ebx
0x18011fc15  jmp     short loc_18011FC23
0x18011fc17  mov     rsi, [rsp+160h+var_110]
0x18011fc1c  jmp     short loc_18011FBFD
0x18011fc1e  mov     rcx, [rsp+160h+pv]
0x18011fc23  test    rbx, rbx
0x18011fc26  jz      loc_18011FD9A
0x18011fc2c  mov     rax, [rdi]
0x18011fc2f  lea     r9, [rsp+160h+var_108]
0x18011fc34  mov     rdx, rcx
0x18011fc37  mov     r8d, r13d
0x18011fc3a  mov     rcx, rdi
0x18011fc3d  mov     rax, [rax+18h]
0x18011fc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fc46  mov     r12d, eax
0x18011fc49  test    eax, eax
0x18011fc4b  js      loc_18011FE52
0x18011fc51  mov     eax, [rsp+160h+var_108]
0x18011fc55  cmp     eax, r13d
0x18011fc58  jnz     loc_18011FD8F
0x18011fc5e  and     dword ptr [rsp+160h+var_F0+4], 0
0x18011fc63  lea     r9, [rsp+160h+var_104]
0x18011fc68  mov     rdx, [rsp+160h+pv]
0x18011fc6d  mov     r8d, r13d
0x18011fc70  mov     dword ptr [rsp+160h+var_F0], eax
0x18011fc74  mov     rcx, rsi
0x18011fc77  mov     rax, [rsi]
0x18011fc7a  add     r15, [rsp+160h+var_F0]
0x18011fc7f  mov     [rsp+160h+var_E8], r15
0x18011fc84  mov     rax, [rax+20h]
0x18011fc88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fc8d  mov     r12d, eax
0x18011fc90  test    eax, eax
0x18011fc92  js      loc_18011FE52
0x18011fc98  mov     eax, [rsp+160h+var_104]
0x18011fc9c  cmp     eax, r13d
0x18011fc9f  jnz     loc_18011FD84
0x18011fca5  and     dword ptr [rsp+160h+var_128+4], 0
0x18011fcaa  and     dword ptr [rsp+160h+var_110+4], 0
0x18011fcaf  and     dword ptr [rbp+60h+var_D8+4], 0
0x18011fcb3  mov     edx, [rsp+160h+var_118]
0x18011fcb7  mov     dword ptr [rsp+160h+var_110], r13d
0x18011fcbc  sub     rbx, [rsp+160h+var_110]
0x18011fcc1  mov     dword ptr [rbp+60h+var_D8], r13d
0x18011fcc5  mov     dword ptr [rsp+160h+var_128], eax
0x18011fcc9  add     r14, [rsp+160h+var_128]
0x18011fcce  cmp     rbx, [rbp+60h+var_D8]
0x18011fcd2  mov     [rbp+60h+var_E0], r14
0x18011fcd6  cmovbe  r13d, ebx
0x18011fcda  test    edx, edx
0x18011fcdc  jnz     loc_18011FC1E
0x18011fce2  test    rbx, rbx
0x18011fce5  jz      loc_18011FC1E
0x18011fceb  and     dword ptr [rbp+60h+var_D0+4], edx
0x18011fcee  lea     ecx, [r13+2000h]
0x18011fcf5  mov     rax, [rdi]
0x18011fcf8  xor     r9d, r9d
0x18011fcfb  mov     dword ptr [rbp+60h+var_D0], ecx
0x18011fcfe  mov     rcx, [rbp+60h+var_D0]
0x18011fd02  neg     rcx
0x18011fd05  mov     rax, [rax+28h]
0x18011fd09  lea     r8d, [r9+1]
0x18011fd0d  mov     rdx, rcx
0x18011fd10  mov     dword ptr [rbp+60h+var_C8], ecx
0x18011fd13  shr     rdx, 20h
0x18011fd17  mov     rcx, rdi
0x18011fd1a  mov     dword ptr [rbp+60h+var_C8+4], edx
0x18011fd1d  mov     rdx, [rbp+60h+var_C8]
0x18011fd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fd26  mov     r12d, eax
0x18011fd29  test    eax, eax
0x18011fd2b  js      loc_18011FE52
0x18011fd31  mov     rax, [rsi]
0x18011fd34  lea     ecx, [r13+2000h]
0x18011fd3b  and     dword ptr [rbp+60h+var_C0+4], 0
0x18011fd3f  xor     r9d, r9d
0x18011fd42  mov     dword ptr [rbp+60h+var_C0], ecx
0x18011fd45  mov     rcx, [rbp+60h+var_C0]
0x18011fd49  mov     rax, [rax+28h]
0x18011fd4d  neg     rcx
0x18011fd50  mov     rdx, rcx
0x18011fd53  mov     dword ptr [rsp+160h+var_120], ecx
0x18011fd57  shr     rdx, 20h
0x18011fd5b  lea     r8d, [r9+1]
0x18011fd5f  mov     dword ptr [rsp+160h+var_120+4], edx
0x18011fd63  mov     rcx, rsi
0x18011fd66  mov     rdx, [rsp+160h+var_120]
0x18011fd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fd70  mov     r12d, eax
0x18011fd73  test    eax, eax
0x18011fd75  js      loc_18011FE52
0x18011fd7b  mov     edx, [rsp+160h+var_118]
0x18011fd7f  jmp     loc_18011FC1E
0x18011fd84  mov     r12d, 8003001Dh
0x18011fd8a  jmp     loc_18011FE52
0x18011fd8f  mov     r12d, 8003001Eh
0x18011fd95  jmp     loc_18011FE52
0x18011fd9a  test    edx, edx
0x18011fd9c  jnz     short loc_18011FE1A
0x18011fd9e  mov     rdx, [rsp+160h+var_100]
0x18011fda3  xor     r9d, r9d
0x18011fda6  mov     rax, [rdi]
0x18011fda9  add     rdx, r15
0x18011fdac  mov     r8, rdx
0x18011fdaf  mov     dword ptr [rsp+160h+var_120], edx
0x18011fdb3  shr     r8, 20h
0x18011fdb7  mov     rcx, rdi
0x18011fdba  mov     dword ptr [rsp+160h+var_120+4], r8d
0x18011fdbf  xor     r8d, r8d
0x18011fdc2  mov     rax, [rax+28h]
0x18011fdc6  mov     [rsp+160h+var_100], rdx
  ... truncated ...
```
