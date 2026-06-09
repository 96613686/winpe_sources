# CExposedDocFile::MarshalInterface(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x18004b0d0`
- end: `0x18004b399`
- name: `?MarshalInterface@CExposedDocFile@@UEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `713`
- prototype: `int(CExposedDocFile *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180018680`
- `0x180018914`
- `0x18001bf68`
- `0x18001c01c`
- `0x18002fa78`
- `0x180042800`
- `0x180043100`
- `0x18004b0d0`
- `0x18004c958`
- `0x18005d67c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!InternalCoStdMarshalObject` at `0x18004b15e`
- `api-ms-win-core-com-private-l1-1-0!InternalCoStdMarshalObject` at `0x18004b1ba`
- `api-ms-win-core-com-private-l1-1-0!InternalCoStdMarshalObject` at `0x18004b15e`
- `api-ms-win-core-com-private-l1-1-0!InternalCoStdMarshalObject` at `0x18004b1ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004b295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004b295`

## pseudocode

```c
__int64 __fastcall CExposedDocFile::MarshalInterface(
        struct CPerContext **this,
        struct IStream *a2,
        const struct _GUID *a3,
        void *a4,
        unsigned int a5,
        void *a6,
        unsigned int a7)
{
  int started; // ebx
  __int64 v12; // r8
  __int64 v13; // r9
  struct CPerContext *v14; // rdx
  char *v15; // rdx
  _QWORD *v16; // rax
  struct CPerContext *v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  struct CPerContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 *v24; // rax
  __int64 v25; // rax
  CProcessSecret *v26; // rcx
  struct CPerContext *v27; // r8
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  int v32; // [rsp+40h] [rbp-A1h] BYREF
  char v33[8]; // [rsp+48h] [rbp-99h] BYREF
  _BYTE v34[16]; // [rsp+50h] [rbp-91h] BYREF
  _QWORD v35[6]; // [rsp+60h] [rbp-81h] BYREF
  __int64 v36; // [rsp+90h] [rbp-51h]
  __int64 v37; // [rsp+98h] [rbp-49h]
  __int64 v38; // [rsp+A0h] [rbp-41h]
  int v39; // [rsp+A8h] [rbp-39h]
  DWORD CurrentProcessId; // [rsp+ACh] [rbp-35h]
  struct _GUID v41; // [rsp+B0h] [rbp-31h] BYREF
  struct CPerContext *v42; // [rsp+C0h] [rbp-21h]
  __int64 v43; // [rsp+C8h] [rbp-19h]

  CSafeMultiHeap::CSafeMultiHeap((CSafeMultiHeap *)v34, this[15]);
  started = CExposedDocFile::Validate((CExposedDocFile *)(this - 7));
  if ( started >= 0 )
  {
    if ( (*((_BYTE *)this[13] + 20) & 0x20) != 0 )
    {
      started = -2147286782;
    }
    else if ( !a5 || a5 == 3 )
    {
      if ( a6 )
      {
        started = -2147286953;
      }
      else
      {
        started = StartMarshal(a2, a3, &IID_IStorage, a7);
        if ( started >= 0 )
        {
          started = InternalCoStdMarshalObject(a2, a3, a4, 0, a5, 0, a7);
          if ( started >= 0 )
          {
            v32 = 0;
            memset_0(v35, 0, 0x70u);
            v14 = this[10];
            if ( v14 )
            {
              v15 = (char *)v14 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
              if ( v15 )
                v35[3] = &v15[-*(_QWORD *)NtCurrentTeb()->ReservedForOle];
            }
            v16 = (_QWORD *)BasedPtr<CDFBasis>::BasedPtr<CDFBasis>(v33, this[13], v12, v13);
            v17 = this[14];
            v35[0] = *v16;
            v20 = *(_QWORD *)BasedPtr<CDFBasis>::BasedPtr<CDFBasis>(v33, v17, v18, v19);
            v21 = this[15];
            v35[4] = v20;
            v42 = v21;
            v22 = *((_QWORD *)v21 + 6);
            if ( v22 )
              v23 = v22 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
            else
              v23 = 0;
            v35[5] = v23;
            v39 = *((_DWORD *)GetTlsSmAllocator() + 9);
            v24 = (__int64 *)*((_QWORD *)GetTlsSmAllocator() + 1);
            if ( v24 )
              v25 = *v24;
            else
              v25 = 0;
            v43 = v25;
            CurrentProcessId = GetCurrentProcessId();
            if ( a5 == 3 )
              CProcessSecret::GetProcessSecret(v26, &v41);
            v27 = this[15];
            v28 = *(_QWORD *)(*((_QWORD *)v27 + 2) + 48LL);
            if ( v28 )
              v36 = v28 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
            else
              v36 = 0;
            v29 = *(_QWORD *)(*((_QWORD *)v27 + 3) + 48LL);
            if ( v29 )
              v37 = v29 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
            else
              v37 = 0;
            if ( (*((_BYTE *)this[13] + 20) & 4) != 0 )
            {
              v30 = *(_QWORD *)(*((_QWORD *)v27 + 4) + 48LL);
              if ( v30 )
                v38 = v30 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
              else
                v38 = 0;
            }
            started = (*(__int64 (__fastcall **)(struct IStream *, _QWORD *, __int64, int *))(*(_QWORD *)a2 + 32LL))(
                        a2,
                        v35,
                        112,
                        &v32);
            if ( started >= 0 && v32 != 112 )
              started = -2147287011;
          }
        }
      }
    }
    else
    {
      started = InternalCoStdMarshalObject(a2, a3, a4, 0, a5, a6, a7);
    }
  }
  CSafeMultiHeap::~CSafeMultiHeap((CSafeMultiHeap *)v34);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18004b0d0  push    rbp
0x18004b0d2  push    rbx
0x18004b0d3  push    rsi
0x18004b0d4  push    rdi
0x18004b0d5  push    r12
0x18004b0d7  push    r13
0x18004b0d9  push    r14
0x18004b0db  push    r15
0x18004b0dd  lea     rbp, [rsp-7]
0x18004b0e2  sub     rsp, 0E8h
0x18004b0e9  mov     rax, cs:__security_cookie
0x18004b0f0  xor     rax, rsp
0x18004b0f3  mov     [rbp+3Fh+var_50], rax
0x18004b0f7  mov     r12, [rbp+3Fh+arg_28]
0x18004b0fb  mov     r15, rdx
0x18004b0fe  mov     rdx, [rcx+78h]; struct CPerContext *
0x18004b102  mov     rsi, rcx
0x18004b105  lea     rcx, [rsp+120h+var_D0]; this
0x18004b10a  mov     r13, r9
0x18004b10d  mov     r14, r8
0x18004b110  call    ??0CSafeMultiHeap@@QEAA@PEAVCPerContext@@@Z; CSafeMultiHeap::CSafeMultiHeap(CPerContext *)
0x18004b115  lea     rcx, [rsi-38h]; this
0x18004b119  call    ?Validate@CExposedDocFile@@QEBAJXZ; CExposedDocFile::Validate(void)
0x18004b11e  mov     ebx, eax
0x18004b120  test    eax, eax
0x18004b122  js      loc_18004B36D
0x18004b128  mov     rax, [rsi+68h]
0x18004b12c  test    byte ptr [rax+14h], 20h
0x18004b130  jnz     loc_18004B368
0x18004b136  mov     edi, [rbp+3Fh+arg_20]
0x18004b139  test    edi, edi
0x18004b13b  jz      short loc_18004B16B
0x18004b13d  cmp     edi, 3
0x18004b140  jz      short loc_18004B16B
0x18004b142  mov     eax, [rbp+3Fh+arg_30]
0x18004b145  xor     r9d, r9d
0x18004b148  mov     [rsp+120h+var_F0], eax
0x18004b14c  mov     r8, r13
0x18004b14f  mov     [rsp+120h+var_F8], r12
0x18004b154  mov     rdx, r14
0x18004b157  mov     rcx, r15
0x18004b15a  mov     [rsp+120h+var_100], edi
0x18004b15e  call    cs:__imp_InternalCoStdMarshalObject
0x18004b164  mov     ebx, eax
0x18004b166  jmp     loc_18004B36D
0x18004b16b  test    r12, r12
0x18004b16e  jz      short loc_18004B17A
0x18004b170  mov     ebx, 80030057h
0x18004b175  jmp     loc_18004B36D
0x18004b17a  mov     r12d, [rbp+3Fh+arg_30]
0x18004b17e  lea     r8, IID_IStorage; struct _GUID *
0x18004b185  mov     r9d, r12d; unsigned int
0x18004b188  mov     rdx, r14; struct _GUID *
0x18004b18b  mov     rcx, r15; struct IStream *
0x18004b18e  call    ?StartMarshal@@YAJPEAUIStream@@AEBU_GUID@@1K@Z; StartMarshal(IStream *,_GUID const &,_GUID const &,ulong)
0x18004b193  mov     ebx, eax
0x18004b195  test    eax, eax
0x18004b197  js      loc_18004B36D
0x18004b19d  mov     [rsp+120h+var_F0], r12d
0x18004b1a2  xor     r9d, r9d
0x18004b1a5  xor     r12d, r12d
0x18004b1a8  mov     r8, r13
0x18004b1ab  mov     [rsp+120h+var_F8], r12
0x18004b1b0  mov     rdx, r14
0x18004b1b3  mov     rcx, r15
0x18004b1b6  mov     [rsp+120h+var_100], edi
0x18004b1ba  call    cs:__imp_InternalCoStdMarshalObject
0x18004b1c0  mov     ebx, eax
0x18004b1c2  test    eax, eax
0x18004b1c4  js      loc_18004B36D
0x18004b1ca  lea     r14d, [r12+70h]
0x18004b1cf  mov     [rsp+120h+var_E0], r12d
0x18004b1d4  mov     r8d, r14d; Size
0x18004b1d7  lea     rcx, [rsp+120h+var_C0]; void *
0x18004b1dc  xor     edx, edx; Val
0x18004b1de  call    memset_0
0x18004b1e3  mov     rdx, [rsi+50h]
0x18004b1e7  test    rdx, rdx
0x18004b1ea  jz      short loc_18004B218
0x18004b1ec  mov     rax, gs:30h
0x18004b1f5  mov     rcx, [rax+1758h]
0x18004b1fc  add     rdx, [rcx]
0x18004b1ff  jz      short loc_18004B218
0x18004b201  mov     rax, gs:30h
0x18004b20a  mov     rcx, [rax+1758h]
0x18004b211  sub     rdx, [rcx]
0x18004b214  mov     [rbp+3Fh+var_A8], rdx
0x18004b218  mov     rdx, [rsi+68h]
0x18004b21c  lea     rcx, [rsp+120h+var_D8]
0x18004b221  call    ??0?$BasedPtr@VCDFBasis@@@@QEAA@PEAVCDFBasis@@@Z; BasedPtr<CDFBasis>::BasedPtr<CDFBasis>(CDFBasis *)
0x18004b226  mov     rdx, [rsi+70h]
0x18004b22a  mov     rcx, [rax]
0x18004b22d  mov     [rsp+120h+var_C0], rcx
0x18004b232  lea     rcx, [rsp+120h+var_D8]
0x18004b237  call    ??0?$BasedPtr@VCDFBasis@@@@QEAA@PEAVCDFBasis@@@Z; BasedPtr<CDFBasis>::BasedPtr<CDFBasis>(CDFBasis *)
0x18004b23c  mov     rcx, [rax]
0x18004b23f  mov     rax, [rsi+78h]
0x18004b243  mov     [rbp+3Fh+var_A0], rcx
0x18004b247  mov     [rbp+3Fh+var_60], rax
0x18004b24b  mov     rdx, [rax+30h]
0x18004b24f  test    rdx, rdx
0x18004b252  jz      short loc_18004B269
0x18004b254  mov     rax, gs:30h
0x18004b25d  mov     rcx, [rax+1758h]
0x18004b264  sub     rdx, [rcx]
0x18004b267  jmp     short loc_18004B26C
0x18004b269  mov     rdx, r12
0x18004b26c  mov     [rbp+3Fh+var_98], rdx
0x18004b270  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18004b275  mov     ecx, [rax+24h]
0x18004b278  mov     [rbp+3Fh+var_78], ecx
0x18004b27b  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18004b280  mov     rax, [rax+8]
0x18004b284  test    rax, rax
0x18004b287  jz      short loc_18004B28E
0x18004b289  mov     rax, [rax]
0x18004b28c  jmp     short loc_18004B291
0x18004b28e  mov     rax, r12
0x18004b291  mov     [rbp+3Fh+var_58], rax
0x18004b295  call    cs:__imp_GetCurrentProcessId
0x18004b29b  mov     [rbp+3Fh+var_74], eax
0x18004b29e  cmp     edi, 3
0x18004b2a1  jnz     short loc_18004B2AC
0x18004b2a3  lea     rdx, [rbp+3Fh+var_70]; struct _GUID *
0x18004b2a7  call    ?GetProcessSecret@CProcessSecret@@QEAAJPEAU_GUID@@@Z; CProcessSecret::GetProcessSecret(_GUID *)
0x18004b2ac  mov     r8, [rsi+78h]
0x18004b2b0  mov     rax, [r8+10h]
0x18004b2b4  mov     rdx, [rax+30h]
0x18004b2b8  test    rdx, rdx
0x18004b2bb  jz      short loc_18004B2D6
0x18004b2bd  mov     rax, gs:30h
0x18004b2c6  mov     rcx, [rax+1758h]
0x18004b2cd  sub     rdx, [rcx]
0x18004b2d0  mov     [rbp+3Fh+var_90], rdx
0x18004b2d4  jmp     short loc_18004B2DA
0x18004b2d6  mov     [rbp+3Fh+var_90], r12
0x18004b2da  mov     rax, [r8+18h]
0x18004b2de  mov     rdx, [rax+30h]
0x18004b2e2  test    rdx, rdx
0x18004b2e5  jz      short loc_18004B300
0x18004b2e7  mov     rax, gs:30h
0x18004b2f0  mov     rcx, [rax+1758h]
0x18004b2f7  sub     rdx, [rcx]
0x18004b2fa  mov     [rbp+3Fh+var_88], rdx
0x18004b2fe  jmp     short loc_18004B304
0x18004b300  mov     [rbp+3Fh+var_88], r12
0x18004b304  mov     rax, [rsi+68h]
0x18004b308  test    byte ptr [rax+14h], 4
0x18004b30c  jz      short loc_18004B338
0x18004b30e  mov     rax, [r8+20h]
0x18004b312  mov     rdx, [rax+30h]
0x18004b316  test    rdx, rdx
0x18004b319  jz      short loc_18004B334
0x18004b31b  mov     rax, gs:30h
0x18004b324  mov     rcx, [rax+1758h]
0x18004b32b  sub     rdx, [rcx]
0x18004b32e  mov     [rbp+3Fh+var_80], rdx
0x18004b332  jmp     short loc_18004B338
0x18004b334  mov     [rbp+3Fh+var_80], r12
0x18004b338  mov     rax, [r15]
0x18004b33b  lea     r9, [rsp+120h+var_E0]
0x18004b340  mov     r8d, r14d
0x18004b343  lea     rdx, [rsp+120h+var_C0]
0x18004b348  mov     rcx, r15
0x18004b34b  mov     rax, [rax+20h]
0x18004b34f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b354  mov     ebx, eax
0x18004b356  test    eax, eax
0x18004b358  js      short loc_18004B36D
0x18004b35a  cmp     [rsp+120h+var_E0], r14d
0x18004b35f  jz      short loc_18004B36D
0x18004b361  mov     ebx, 8003001Dh
0x18004b366  jmp     short loc_18004B36D
0x18004b368  mov     ebx, 80030102h
0x18004b36d  lea     rcx, [rsp+120h+var_D0]; this
0x18004b372  call    ??1CSafeMultiHeap@@QEAA@XZ; CSafeMultiHeap::~CSafeMultiHeap(void)
0x18004b377  mov     eax, ebx
0x18004b379  mov     rcx, [rbp+3Fh+var_50]
0x18004b37d  xor     rcx, rsp; StackCookie
0x18004b380  call    __security_check_cookie
0x18004b385  add     rsp, 0E8h
0x18004b38c  pop     r15
0x18004b38e  pop     r14
0x18004b390  pop     r13
0x18004b392  pop     r12
0x18004b394  pop     rdi
0x18004b395  pop     rsi
0x18004b396  pop     rbx
0x18004b397  pop     rbp
0x18004b398  retn
```
