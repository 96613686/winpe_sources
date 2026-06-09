# CExposedStream::MarshalInterface(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x18004dc00`
- end: `0x18004df65`
- name: `?MarshalInterface@CExposedStream@@UEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `869`
- prototype: `int(CExposedStream *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b8d0`
- `0x180018680`
- `0x180018914`
- `0x18001bf68`
- `0x18002fa78`
- `0x180042800`
- `0x180043100`
- `0x18004c958`
- `0x18004dc00`
- `0x18005d67c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004de94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004de94`
- `api-ms-win-core-com-l1-1-0!CoGetStandardMarshal` at `0x18004dc98`
- `api-ms-win-core-com-l1-1-0!CoGetStandardMarshal` at `0x18004dd3d`
- `api-ms-win-core-com-l1-1-0!CoGetStandardMarshal` at `0x18004dc98`
- `api-ms-win-core-com-l1-1-0!CoGetStandardMarshal` at `0x18004dd3d`

## pseudocode

```c
__int64 __fastcall CExposedStream::MarshalInterface(
        struct CPerContext **this,
        struct IStream *a2,
        const struct _GUID *a3,
        IUnknown *a4,
        DWORD dwDestContext,
        void *pvDestContext,
        DWORD mshlflags)
{
  HRESULT started; // ebx
  __int64 v12; // r8
  __int64 v13; // r9
  struct CPerContext *v14; // rdx
  char *v15; // rdx
  struct CPerContext *v16; // rdx
  char *v17; // rdx
  __int64 *v18; // rax
  struct CPerContext *v19; // rdx
  char *v20; // rdx
  struct CPerContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 *v24; // rax
  __int64 v25; // rax
  CProcessSecret *v26; // rcx
  struct CPerContext *v27; // r8
  __int64 v28; // rdx
  __int64 v29; // rdx
  LPMARSHAL ppMarshal; // [rsp+40h] [rbp-A1h] BYREF
  LPMARSHAL v32; // [rsp+48h] [rbp-99h] BYREF
  _BYTE v33[16]; // [rsp+50h] [rbp-91h] BYREF
  char v34[8]; // [rsp+60h] [rbp-81h] BYREF
  char *v35; // [rsp+68h] [rbp-79h]
  char *v36; // [rsp+70h] [rbp-71h]
  char *v37; // [rsp+78h] [rbp-69h]
  __int64 v38; // [rsp+80h] [rbp-61h]
  __int64 v39; // [rsp+88h] [rbp-59h]
  __int64 v40; // [rsp+90h] [rbp-51h]
  __int64 v41; // [rsp+98h] [rbp-49h]
  int v42; // [rsp+A8h] [rbp-39h]
  DWORD CurrentProcessId; // [rsp+ACh] [rbp-35h]
  struct _GUID v44; // [rsp+B0h] [rbp-31h] BYREF
  struct CPerContext *v45; // [rsp+C0h] [rbp-21h]
  __int64 v46; // [rsp+C8h] [rbp-19h]

  CSafeMultiHeap::CSafeMultiHeap((CSafeMultiHeap *)v33, this[14]);
  started = CExposedStream::Validate((CExposedStream *)(this - 1));
  if ( started >= 0 )
  {
    if ( (*((_BYTE *)this[12] + 20) & 0x20) != 0 )
    {
      started = -2147286782;
    }
    else if ( !dwDestContext || dwDestContext == 3 )
    {
      if ( pvDestContext )
      {
        started = -2147286953;
      }
      else
      {
        started = StartMarshal(a2, a3, &IID_IStream, mshlflags);
        if ( started >= 0 )
        {
          v32 = 0;
          started = CoGetStandardMarshal(a3, a4, dwDestContext, 0, mshlflags, &v32);
          if ( started >= 0 )
          {
            started = ((__int64 (__fastcall *)(LPMARSHAL, struct IStream *, const struct _GUID *, IUnknown *, DWORD, _QWORD, DWORD))v32->lpVtbl->MarshalInterface)(
                        v32,
                        a2,
                        a3,
                        a4,
                        dwDestContext,
                        0,
                        mshlflags);
            ((void (__fastcall *)(LPMARSHAL))v32->lpVtbl->Release)(v32);
            if ( started >= 0 )
            {
              LODWORD(ppMarshal) = 0;
              memset_0(v34, 0, 0x70u);
              v14 = this[9];
              if ( v14 )
              {
                v15 = (char *)v14 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
                if ( v15 )
                  v37 = &v15[-*(_QWORD *)NtCurrentTeb()->ReservedForOle];
              }
              v16 = this[12];
              if ( v16 )
                v17 = (char *)v16 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
              else
                v17 = 0;
              v35 = v17;
              v18 = (__int64 *)BasedPtr<CDFBasis>::BasedPtr<CDFBasis>(&v32, this[13], v12, v13);
              v19 = this[16];
              v38 = *v18;
              if ( v19 )
                v20 = (char *)v19 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
              else
                v20 = 0;
              v21 = this[14];
              v36 = v20;
              v45 = v21;
              v22 = *((_QWORD *)v21 + 6);
              if ( v22 )
                v23 = v22 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
              else
                v23 = 0;
              v39 = v23;
              v42 = *((_DWORD *)GetTlsSmAllocator() + 9);
              v24 = (__int64 *)*((_QWORD *)GetTlsSmAllocator() + 1);
              if ( v24 )
                v25 = *v24;
              else
                v25 = 0;
              v46 = v25;
              CurrentProcessId = GetCurrentProcessId();
              if ( dwDestContext == 3 )
                CProcessSecret::GetProcessSecret(v26, &v44);
              v27 = this[14];
              v28 = *(_QWORD *)(*((_QWORD *)v27 + 2) + 48LL);
              if ( v28 )
                v40 = v28 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
              else
                v40 = 0;
              v29 = *(_QWORD *)(*((_QWORD *)v27 + 3) + 48LL);
              if ( v29 )
                v41 = v29 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
              else
                v41 = 0;
              started = (*(__int64 (__fastcall **)(struct IStream *, char *, __int64, LPMARSHAL *))(*(_QWORD *)a2 + 32LL))(
                          a2,
                          v34,
                          112,
                          &ppMarshal);
              if ( started >= 0 && (_DWORD)ppMarshal != 112 )
                started = -2147287011;
            }
          }
        }
      }
    }
    else
    {
      ppMarshal = 0;
      started = CoGetStandardMarshal(a3, a4, dwDestContext, pvDestContext, mshlflags, &ppMarshal);
      if ( started >= 0 )
      {
        started = ((__int64 (__fastcall *)(LPMARSHAL, struct IStream *, const struct _GUID *, IUnknown *, DWORD, void *, DWORD))ppMarshal->lpVtbl->MarshalInterface)(
                    ppMarshal,
                    a2,
                    a3,
                    a4,
                    dwDestContext,
                    pvDestContext,
                    mshlflags);
        ((void (__fastcall *)(LPMARSHAL))ppMarshal->lpVtbl->Release)(ppMarshal);
      }
    }
  }
  CSafeMultiHeap::~CSafeMultiHeap((CSafeMultiHeap *)v33);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18004dc00  push    rbp
0x18004dc02  push    rbx
0x18004dc03  push    rsi
0x18004dc04  push    rdi
0x18004dc05  push    r12
0x18004dc07  push    r13
0x18004dc09  push    r14
0x18004dc0b  push    r15
0x18004dc0d  lea     rbp, [rsp-7]
0x18004dc12  sub     rsp, 0E8h
0x18004dc19  mov     rax, cs:__security_cookie
0x18004dc20  xor     rax, rsp
0x18004dc23  mov     [rbp+3Fh+var_50], rax
0x18004dc27  mov     r15, [rbp+3Fh+pvDestContext]
0x18004dc2b  mov     r13, rdx
0x18004dc2e  mov     rdx, [rcx+70h]; struct CPerContext *
0x18004dc32  mov     rdi, rcx
0x18004dc35  lea     rcx, [rsp+120h+var_D0]; this
0x18004dc3a  mov     r12, r9
0x18004dc3d  mov     r14, r8
0x18004dc40  call    ??0CSafeMultiHeap@@QEAA@PEAVCPerContext@@@Z; CSafeMultiHeap::CSafeMultiHeap(CPerContext *)
0x18004dc45  lea     rcx, [rdi-8]; this
0x18004dc49  call    ?Validate@CExposedStream@@QEBAJXZ; CExposedStream::Validate(void)
0x18004dc4e  mov     ebx, eax
0x18004dc50  test    eax, eax
0x18004dc52  js      loc_18004DF39
0x18004dc58  mov     rax, [rdi+60h]
0x18004dc5c  test    byte ptr [rax+14h], 20h
0x18004dc60  jnz     loc_18004DF34
0x18004dc66  mov     esi, [rbp+3Fh+dwDestContext]
0x18004dc69  test    esi, esi
0x18004dc6b  jz      short loc_18004DCE7
0x18004dc6d  cmp     esi, 3
0x18004dc70  jz      short loc_18004DCE7
0x18004dc72  mov     edi, [rbp+3Fh+arg_30]
0x18004dc75  lea     rax, [rsp+120h+var_E0]
0x18004dc7a  mov     [rsp+120h+ppMarshal], rax; ppMarshal
0x18004dc7f  mov     r9, r15; pvDestContext
0x18004dc82  mov     r8d, esi; dwDestContext
0x18004dc85  mov     [rsp+120h+mshlflags], edi; mshlflags
0x18004dc89  mov     rdx, r12; pUnk
0x18004dc8c  mov     [rsp+120h+var_E0], 0
0x18004dc95  mov     rcx, r14; riid
0x18004dc98  call    cs:__imp_CoGetStandardMarshal
0x18004dc9e  mov     ebx, eax
0x18004dca0  test    eax, eax
0x18004dca2  js      loc_18004DF39
0x18004dca8  mov     rcx, [rsp+120h+var_E0]
0x18004dcad  mov     r9, r12
0x18004dcb0  mov     [rsp+120h+var_F0], edi
0x18004dcb4  mov     r8, r14
0x18004dcb7  mov     [rsp+120h+ppMarshal], r15
0x18004dcbc  mov     rdx, r13
0x18004dcbf  mov     [rsp+120h+mshlflags], esi
0x18004dcc3  mov     rax, [rcx]
0x18004dcc6  mov     rax, [rax+28h]
0x18004dcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dccf  mov     rcx, [rsp+120h+var_E0]
0x18004dcd4  mov     ebx, eax
0x18004dcd6  mov     rax, [rcx]
0x18004dcd9  mov     rax, [rax+10h]
0x18004dcdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dce2  jmp     loc_18004DF39
0x18004dce7  test    r15, r15
0x18004dcea  jz      short loc_18004DCF6
0x18004dcec  mov     ebx, 80030057h
0x18004dcf1  jmp     loc_18004DF39
0x18004dcf6  mov     r15d, [rbp+3Fh+arg_30]
0x18004dcfa  lea     r8, IID_IStream; struct _GUID *
0x18004dd01  mov     r9d, r15d; unsigned int
0x18004dd04  mov     rdx, r14; struct _GUID *
0x18004dd07  mov     rcx, r13; struct IStream *
0x18004dd0a  call    ?StartMarshal@@YAJPEAUIStream@@AEBU_GUID@@1K@Z; StartMarshal(IStream *,_GUID const &,_GUID const &,ulong)
0x18004dd0f  mov     ebx, eax
0x18004dd11  test    eax, eax
0x18004dd13  js      loc_18004DF39
0x18004dd19  lea     rax, [rsp+120h+var_D8]
0x18004dd1e  mov     [rsp+120h+var_D8], 0
0x18004dd27  mov     [rsp+120h+ppMarshal], rax; ppMarshal
0x18004dd2c  xor     r9d, r9d; pvDestContext
0x18004dd2f  mov     r8d, esi; dwDestContext
0x18004dd32  mov     [rsp+120h+mshlflags], r15d; mshlflags
0x18004dd37  mov     rdx, r12; pUnk
0x18004dd3a  mov     rcx, r14; riid
0x18004dd3d  call    cs:__imp_CoGetStandardMarshal
0x18004dd43  mov     ebx, eax
0x18004dd45  test    eax, eax
0x18004dd47  js      loc_18004DF39
0x18004dd4d  mov     rcx, [rsp+120h+var_D8]
0x18004dd52  mov     r9, r12
0x18004dd55  mov     [rsp+120h+var_F0], r15d
0x18004dd5a  mov     r8, r14
0x18004dd5d  xor     r15d, r15d
0x18004dd60  mov     rdx, r13
0x18004dd63  mov     [rsp+120h+ppMarshal], r15
0x18004dd68  mov     rax, [rcx]
0x18004dd6b  mov     [rsp+120h+mshlflags], esi
0x18004dd6f  mov     rax, [rax+28h]
0x18004dd73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd78  mov     rcx, [rsp+120h+var_D8]
0x18004dd7d  mov     ebx, eax
0x18004dd7f  mov     rax, [rcx]
0x18004dd82  mov     rax, [rax+10h]
0x18004dd86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd8b  test    ebx, ebx
0x18004dd8d  js      loc_18004DF39
0x18004dd93  lea     r14d, [r15+70h]
0x18004dd97  mov     dword ptr [rsp+120h+var_E0], r15d
0x18004dd9c  mov     r8d, r14d; Size
0x18004dd9f  lea     rcx, [rsp+120h+var_C0]; void *
0x18004dda4  xor     edx, edx; Val
0x18004dda6  call    memset_0
0x18004ddab  mov     rdx, [rdi+48h]
0x18004ddaf  test    rdx, rdx
0x18004ddb2  jz      short loc_18004DDE0
0x18004ddb4  mov     rax, gs:30h
0x18004ddbd  mov     rcx, [rax+1758h]
0x18004ddc4  add     rdx, [rcx]
0x18004ddc7  jz      short loc_18004DDE0
0x18004ddc9  mov     rax, gs:30h
0x18004ddd2  mov     rcx, [rax+1758h]
0x18004ddd9  sub     rdx, [rcx]
0x18004dddc  mov     [rbp+3Fh+var_A8], rdx
0x18004dde0  mov     rdx, [rdi+60h]
0x18004dde4  test    rdx, rdx
0x18004dde7  jz      short loc_18004DDFE
0x18004dde9  mov     rax, gs:30h
0x18004ddf2  mov     rcx, [rax+1758h]
0x18004ddf9  sub     rdx, [rcx]
0x18004ddfc  jmp     short loc_18004DE01
0x18004ddfe  mov     rdx, r15
0x18004de01  mov     [rbp+3Fh+var_B8], rdx
0x18004de05  lea     rcx, [rsp+120h+var_D8]
0x18004de0a  mov     rdx, [rdi+68h]
0x18004de0e  call    ??0?$BasedPtr@VCDFBasis@@@@QEAA@PEAVCDFBasis@@@Z; BasedPtr<CDFBasis>::BasedPtr<CDFBasis>(CDFBasis *)
0x18004de13  mov     rdx, [rdi+80h]
0x18004de1a  mov     rcx, [rax]
0x18004de1d  mov     [rbp+3Fh+var_A0], rcx
0x18004de21  test    rdx, rdx
0x18004de24  jz      short loc_18004DE3B
0x18004de26  mov     rax, gs:30h
0x18004de2f  mov     rcx, [rax+1758h]
0x18004de36  sub     rdx, [rcx]
0x18004de39  jmp     short loc_18004DE3E
0x18004de3b  mov     rdx, r15
0x18004de3e  mov     rax, [rdi+70h]
0x18004de42  mov     [rbp+3Fh+var_B0], rdx
0x18004de46  mov     [rbp+3Fh+var_60], rax
0x18004de4a  mov     rdx, [rax+30h]
0x18004de4e  test    rdx, rdx
0x18004de51  jz      short loc_18004DE68
0x18004de53  mov     rax, gs:30h
0x18004de5c  mov     rcx, [rax+1758h]
0x18004de63  sub     rdx, [rcx]
0x18004de66  jmp     short loc_18004DE6B
0x18004de68  mov     rdx, r15
0x18004de6b  mov     [rbp+3Fh+var_98], rdx
0x18004de6f  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18004de74  mov     ecx, [rax+24h]
0x18004de77  mov     [rbp+3Fh+var_78], ecx
0x18004de7a  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18004de7f  mov     rax, [rax+8]
0x18004de83  test    rax, rax
0x18004de86  jz      short loc_18004DE8D
0x18004de88  mov     rax, [rax]
0x18004de8b  jmp     short loc_18004DE90
0x18004de8d  mov     rax, r15
0x18004de90  mov     [rbp+3Fh+var_58], rax
0x18004de94  call    cs:__imp_GetCurrentProcessId
0x18004de9a  mov     [rbp+3Fh+var_74], eax
0x18004de9d  cmp     esi, 3
0x18004dea0  jnz     short loc_18004DEAB
0x18004dea2  lea     rdx, [rbp+3Fh+var_70]; struct _GUID *
0x18004dea6  call    ?GetProcessSecret@CProcessSecret@@QEAAJPEAU_GUID@@@Z; CProcessSecret::GetProcessSecret(_GUID *)
0x18004deab  mov     r8, [rdi+70h]
0x18004deaf  mov     rax, [r8+10h]
0x18004deb3  mov     rdx, [rax+30h]
0x18004deb7  test    rdx, rdx
0x18004deba  jz      short loc_18004DED5
0x18004debc  mov     rax, gs:30h
0x18004dec5  mov     rcx, [rax+1758h]
0x18004decc  sub     rdx, [rcx]
0x18004decf  mov     [rbp+3Fh+var_90], rdx
0x18004ded3  jmp     short loc_18004DED9
0x18004ded5  mov     [rbp+3Fh+var_90], r15
0x18004ded9  mov     rax, [r8+18h]
0x18004dedd  mov     rdx, [rax+30h]
0x18004dee1  test    rdx, rdx
0x18004dee4  jz      short loc_18004DEFF
0x18004dee6  mov     rax, gs:30h
0x18004deef  mov     rcx, [rax+1758h]
0x18004def6  sub     rdx, [rcx]
0x18004def9  mov     [rbp+3Fh+var_88], rdx
0x18004defd  jmp     short loc_18004DF03
0x18004deff  mov     [rbp+3Fh+var_88], r15
0x18004df03  mov     rax, [r13+0]
0x18004df07  lea     r9, [rsp+120h+var_E0]
0x18004df0c  mov     r8d, r14d
0x18004df0f  lea     rdx, [rsp+120h+var_C0]
0x18004df14  mov     rcx, r13
0x18004df17  mov     rax, [rax+20h]
0x18004df1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df20  mov     ebx, eax
0x18004df22  test    eax, eax
0x18004df24  js      short loc_18004DF39
0x18004df26  cmp     dword ptr [rsp+120h+var_E0], r14d
0x18004df2b  jz      short loc_18004DF39
0x18004df2d  mov     ebx, 8003001Dh
0x18004df32  jmp     short loc_18004DF39
0x18004df34  mov     ebx, 80030102h
0x18004df39  lea     rcx, [rsp+120h+var_D0]; this
0x18004df3e  call    ??1CSafeMultiHeap@@QEAA@XZ; CSafeMultiHeap::~CSafeMultiHeap(void)
0x18004df43  mov     eax, ebx
0x18004df45  mov     rcx, [rbp+3Fh+var_50]
0x18004df49  xor     rcx, rsp; StackCookie
0x18004df4c  call    __security_check_cookie
0x18004df51  add     rsp, 0E8h
0x18004df58  pop     r15
0x18004df5a  pop     r14
0x18004df5c  pop     r13
0x18004df5e  pop     r12
0x18004df60  pop     rdi
0x18004df61  pop     rsi
0x18004df62  pop     rbx
0x18004df63  pop     rbp
0x18004df64  retn
```
