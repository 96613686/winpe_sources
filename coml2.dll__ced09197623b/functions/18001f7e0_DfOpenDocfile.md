# DfOpenDocfile

- ea: `0x18001f7e0`
- end: `0x18001faea`
- name: `DfOpenDocfile`
- size: `778`
- prototype: `__int64 __fastcall(unsigned __int16 *, void *, unsigned int, unsigned __int16 **, void *, __int64, int, struct IStorage **)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f7a0`
- `0x180033544`

## callees

- `0x180015258`
- `0x18001c2ac`
- `0x18001e2f0`
- `0x18001eeb4`
- `0x18001eef0`
- `0x18001f7e0`
- `0x18001faf0`
- `0x180042800`
- `0x180043100`
- `0x18004e778`
- `0x180060478`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18001f9cb`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18001f9cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fa68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fa68`

## pseudocode

```c
__int64 __fastcall DfOpenDocfile(
        unsigned __int16 *a1,
        void *a2,
        unsigned int a3,
        unsigned __int16 **a4,
        void *a5,
        unsigned int *a6,
        int a7,
        struct IStorage **a8)
{
  void *v8; // r10
  const unsigned __int16 *v12; // r15
  struct CExposedDocFile *v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // r8
  unsigned __int16 *v19; // rcx
  int v20; // ebx
  unsigned int v21; // eax
  unsigned int v22; // r10d
  unsigned __int64 v24; // rcx
  struct IMalloc *v25; // [rsp+38h] [rbp-C8h]
  struct CExposedDocFile *v26; // [rsp+40h] [rbp-C0h] BYREF
  void *v27; // [rsp+48h] [rbp-B8h]
  PVOID ReservedForOle; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v29; // [rsp+58h] [rbp-A8h]
  LPVOID pv[10]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v31[264]; // [rsp+B0h] [rbp-50h] BYREF

  v8 = a5;
  v27 = a5;
  v29 = a6;
  v12 = a1;
  v26 = 0;
  v13 = 0;
  if ( !a8 )
    goto LABEL_24;
  *a8 = 0;
  if ( !a2 )
  {
    if ( a1 )
    {
      v14 = 260;
      v15 = 260;
      do
      {
        if ( !*a1 )
          break;
        ++a1;
        --v15;
      }
      while ( v15 );
      if ( v15 )
      {
        v16 = 2147483646;
        v17 = v31;
        v18 = v12;
        do
        {
          if ( !v16 )
            break;
          if ( !*v18 )
            break;
          *v17++ = *v18++;
          --v16;
          --v14;
        }
        while ( v14 );
        v19 = v17 - 1;
        if ( v14 )
          v19 = v17;
        *v19 = 0;
        goto LABEL_15;
      }
    }
LABEL_28:
    v20 = -2147286788;
    goto LABEL_25;
  }
  memset_0(pv, 0, sizeof(pv));
  if ( !(unsigned int)IsValidStgInterface(a2) )
  {
LABEL_24:
    v20 = -2147287031;
    goto LABEL_25;
  }
  v20 = (*(__int64 (__fastcall **)(void *, LPVOID *, _QWORD))(*(_QWORD *)a2 + 136LL))(a2, pv, 0);
  if ( v20 < 0 )
    goto LABEL_25;
  v24 = -1;
  do
    ++v24;
  while ( *((_WORD *)pv[0] + v24) );
  if ( v24 > 0x104 )
    goto LABEL_28;
  StringCbCopyW(v31, 0x208u, (const unsigned __int16 *)pv[0]);
  CoTaskMemFree(pv[0]);
  v8 = v27;
LABEL_15:
  if ( (a3 & 0x8000000) != 0 )
  {
    v20 = DfOpenSimpDocfile(v12, a3, v8, a8);
    goto LABEL_25;
  }
  v20 = VerifyPerms(a3, 1);
  if ( v20 < 0 )
    goto LABEL_25;
  if ( (a3 & 0x21000) != 0 )
  {
    v20 = -2147286785;
    goto LABEL_25;
  }
  if ( !a4 )
    goto LABEL_19;
  if ( (a3 & 3) != 2 )
  {
    v20 = -2147287035;
    goto LABEL_25;
  }
  v20 = ValidateSNB(a4);
  if ( v20 >= 0 )
  {
LABEL_19:
    if ( (a3 & 0x4000000) != 0 )
    {
      v20 = -2147287039;
    }
    else if ( !a2 || (v20 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)a2 + 16LL))(a2), v20 >= 0) )
    {
      ReservedForOle = NtCurrentTeb()->ReservedForOle;
      if ( ReservedForOle || (v20 = InternalTlsAllocData(&ReservedForOle), v20 >= 0) )
      {
        Microsoft::WRL::ComPtr<CExposedDocFile>::InternalRelease(&v26);
        v21 = ModeToDFlags(a3);
        v20 = DfFromName(v31, v21, v22, a4, &v26, v29, v27, v25);
        if ( v20 >= 0 )
          *a8 = (struct IStorage *)v26;
        else
          v13 = v26;
      }
    }
  }
LABEL_25:
  if ( v13 )
    (*(void (__fastcall **)(struct CExposedDocFile *))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18001f7e0  push    rbp
0x18001f7e2  push    rbx
0x18001f7e3  push    rsi
0x18001f7e4  push    rdi
0x18001f7e5  push    r12
0x18001f7e7  push    r13
0x18001f7e9  push    r14
0x18001f7eb  push    r15
0x18001f7ed  lea     rbp, [rsp-1D8h]
0x18001f7f5  sub     rsp, 2D8h
0x18001f7fc  mov     rax, cs:__security_cookie
0x18001f803  xor     rax, rsp
0x18001f806  mov     [rbp+210h+var_50], rax
0x18001f80d  mov     r12, [rbp+210h+arg_38]
0x18001f814  xor     ebx, ebx
0x18001f816  mov     r10, [rbp+210h+arg_20]
0x18001f81d  mov     r13, r9
0x18001f820  mov     rax, [rbp+210h+arg_28]
0x18001f827  mov     esi, r8d
0x18001f82a  mov     [rsp+310h+var_2C8], r10
0x18001f82f  mov     r14, rdx
0x18001f832  mov     [rsp+310h+var_2B8], rax
0x18001f837  mov     r15, rcx
0x18001f83a  mov     [rsp+310h+var_2D0], rbx
0x18001f83f  mov     edi, ebx
0x18001f841  test    r12, r12
0x18001f844  jz      loc_18001F985
0x18001f84a  mov     [r12], rbx
0x18001f84e  test    rdx, rdx
0x18001f851  jnz     loc_18001F9EE
0x18001f857  test    rcx, rcx
0x18001f85a  jz      loc_18001F9B4
0x18001f860  mov     eax, 104h
0x18001f865  mov     edx, eax
0x18001f867  cmp     [rcx], bx
0x18001f86a  jz      short loc_18001F876
0x18001f86c  add     rcx, 2
0x18001f870  sub     rdx, 1
0x18001f874  jnz     short loc_18001F867
0x18001f876  test    rdx, rdx
0x18001f879  jz      loc_18001F9B4
0x18001f87f  mov     ecx, 7FFFFFFEh
0x18001f884  lea     rdx, [rbp+210h+var_260]
0x18001f888  mov     r8, r15
0x18001f88b  test    rcx, rcx
0x18001f88e  jz      short loc_18001F8AF
0x18001f890  movzx   r9d, word ptr [r8]
0x18001f894  test    r9w, r9w
0x18001f898  jz      short loc_18001F8AF
0x18001f89a  mov     [rdx], r9w
0x18001f89e  add     r8, 2
0x18001f8a2  add     rdx, 2
0x18001f8a6  dec     rcx
0x18001f8a9  sub     rax, 1
0x18001f8ad  jnz     short loc_18001F88B
0x18001f8af  test    rax, rax
0x18001f8b2  lea     rcx, [rdx-2]
0x18001f8b6  cmovnz  rcx, rdx
0x18001f8ba  mov     [rcx], bx
0x18001f8bd  bt      esi, 1Bh
0x18001f8c1  jb      loc_18001FA78
0x18001f8c7  mov     edx, 1; int
0x18001f8cc  mov     ecx, esi; unsigned int
0x18001f8ce  call    ?VerifyPerms@@YAJKH@Z; VerifyPerms(ulong,int)
0x18001f8d3  xor     r15d, r15d
0x18001f8d6  mov     ebx, eax
0x18001f8d8  test    eax, eax
0x18001f8da  js      loc_18001F98A
0x18001f8e0  test    esi, 21000h
0x18001f8e6  jnz     loc_18001FA8F
0x18001f8ec  test    r13, r13
0x18001f8ef  jnz     loc_18001FA99
0x18001f8f5  bt      esi, 1Ah
0x18001f8f9  jb      loc_18001FAC2
0x18001f8ff  test    r14, r14
0x18001f902  jnz     loc_18001FACC
0x18001f908  mov     rax, gs:30h
0x18001f911  mov     rcx, [rax+1758h]
0x18001f918  mov     [rsp+310h+var_2C0], rcx
0x18001f91d  test    rcx, rcx
0x18001f920  jz      loc_18001F9C6
0x18001f926  lea     rcx, [rsp+310h+var_2D0]
0x18001f92b  call    ?InternalRelease@?$ComPtr@VCExposedDocFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CExposedDocFile>::InternalRelease(void)
0x18001f930  mov     r10d, [rbp+210h+arg_30]
0x18001f937  mov     ecx, esi; unsigned int
0x18001f939  shr     r10d, 14h
0x18001f93d  and     r10d, 200h
0x18001f944  call    ?ModeToDFlags@@YAKK@Z; ModeToDFlags(ulong)
0x18001f949  mov     edx, eax; unsigned int
0x18001f94b  lea     rcx, [rbp+210h+var_260]; unsigned __int16 *
0x18001f94f  mov     rax, [rsp+310h+var_2C8]
0x18001f954  mov     r9, r13; unsigned __int16 **
0x18001f957  mov     [rsp+310h+var_2E0], rax; void *
0x18001f95c  mov     r8d, r10d; unsigned int
0x18001f95f  mov     rax, [rsp+310h+var_2B8]
0x18001f964  mov     [rsp+310h+var_2E8], rax; unsigned int *
0x18001f969  lea     rax, [rsp+310h+var_2D0]
0x18001f96e  mov     [rsp+310h+var_2F0], rax; struct CExposedDocFile **
0x18001f973  call    ?DfFromName@@YAJPEBGKKPEAPEAGPEAPEAVCExposedDocFile@@PEAKPEAXPEAU_GUID@@@Z; DfFromName(ushort const *,ulong,ulong,ushort * *,CExposedDocFile * *,ulong *,void *,_GUID *)
0x18001f978  mov     ebx, eax
0x18001f97a  test    eax, eax
0x18001f97c  jns     short loc_18001F9BB
0x18001f97e  mov     rdi, [rsp+310h+var_2D0]
0x18001f983  jmp     short loc_18001F98A
0x18001f985  mov     ebx, 80030009h
0x18001f98a  test    rdi, rdi
0x18001f98d  jnz     short loc_18001F9DD
0x18001f98f  mov     eax, ebx
0x18001f991  mov     rcx, [rbp+210h+var_50]
0x18001f998  xor     rcx, rsp; StackCookie
0x18001f99b  call    __security_check_cookie
0x18001f9a0  add     rsp, 2D8h
0x18001f9a7  pop     r15
0x18001f9a9  pop     r14
0x18001f9ab  pop     r13
0x18001f9ad  pop     r12
0x18001f9af  pop     rdi
0x18001f9b0  pop     rsi
0x18001f9b1  pop     rbx
0x18001f9b2  pop     rbp
0x18001f9b3  retn
0x18001f9b4  mov     ebx, 800300FCh
0x18001f9b9  jmp     short loc_18001F98A
0x18001f9bb  mov     rax, [rsp+310h+var_2D0]
0x18001f9c0  mov     [r12], rax
0x18001f9c4  jmp     short loc_18001F98A
0x18001f9c6  lea     rcx, [rsp+310h+var_2C0]
0x18001f9cb  call    cs:__imp_InternalTlsAllocData
0x18001f9d1  mov     ebx, eax
0x18001f9d3  test    eax, eax
0x18001f9d5  jns     loc_18001F926
0x18001f9db  jmp     short loc_18001F98A
0x18001f9dd  mov     rax, [rdi]
0x18001f9e0  mov     rcx, rdi
0x18001f9e3  mov     rax, [rax+10h]
0x18001f9e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9ec  jmp     short loc_18001F98F
0x18001f9ee  xor     edx, edx; Val
0x18001f9f0  lea     rcx, [rsp+310h+pv]; void *
0x18001f9f5  lea     r8d, [rdx+50h]; Size
0x18001f9f9  call    memset_0
0x18001f9fe  mov     rcx, r14; void *
0x18001fa01  call    ?IsValidStgInterface@@YAHPEAX@Z; IsValidStgInterface(void *)
0x18001fa06  test    eax, eax
0x18001fa08  jz      loc_18001F985
0x18001fa0e  mov     rax, [r14]
0x18001fa11  lea     rdx, [rsp+310h+pv]
0x18001fa16  xor     r8d, r8d
0x18001fa19  mov     rcx, r14
0x18001fa1c  mov     rax, [rax+88h]
0x18001fa23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa28  mov     ebx, eax
0x18001fa2a  test    eax, eax
0x18001fa2c  js      loc_18001F98A
0x18001fa32  mov     r8, [rsp+310h+pv]; unsigned __int16 *
0x18001fa37  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001fa3b  xor     ebx, ebx
0x18001fa3d  inc     rcx
0x18001fa40  cmp     [r8+rcx*2], bx
0x18001fa45  jnz     short loc_18001FA3D
0x18001fa47  mov     eax, 104h
0x18001fa4c  cmp     rcx, rax
0x18001fa4f  ja      loc_18001F9B4
0x18001fa55  mov     edx, 208h; unsigned __int64
0x18001fa5a  lea     rcx, [rbp+210h+var_260]; unsigned __int16 *
0x18001fa5e  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001fa63  mov     rcx, [rsp+310h+pv]; pv
0x18001fa68  call    cs:__imp_CoTaskMemFree
0x18001fa6e  mov     r10, [rsp+310h+var_2C8]
0x18001fa73  jmp     loc_18001F8BD
0x18001fa78  mov     r9, r12; struct IStorage **
0x18001fa7b  mov     r8, r10; void *
0x18001fa7e  mov     edx, esi; unsigned int
0x18001fa80  mov     rcx, r15; unsigned __int16 *
0x18001fa83  call    ?DfOpenSimpDocfile@@YAJPEBGKPEAXPEAPEAUIStorage@@@Z; DfOpenSimpDocfile(ushort const *,ulong,void *,IStorage * *)
0x18001fa88  mov     ebx, eax
0x18001fa8a  jmp     loc_18001F98A
0x18001fa8f  mov     ebx, 800300FFh
0x18001fa94  jmp     loc_18001F98A
0x18001fa99  mov     eax, esi
0x18001fa9b  and     al, 3
0x18001fa9d  cmp     al, 2
0x18001fa9f  jz      short loc_18001FAAB
0x18001faa1  mov     ebx, 80030005h
0x18001faa6  jmp     loc_18001F98A
0x18001faab  mov     rcx, r13; unsigned __int16 **
0x18001faae  call    ?ValidateSNB@@YAJPEAPEAG@Z; ValidateSNB(ushort * *)
0x18001fab3  mov     ebx, eax
0x18001fab5  test    eax, eax
0x18001fab7  js      loc_18001F98A
0x18001fabd  jmp     loc_18001F8F5
0x18001fac2  mov     ebx, 80030001h
0x18001fac7  jmp     loc_18001F98A
0x18001facc  mov     rax, [r14]
0x18001facf  mov     rcx, r14
0x18001fad2  mov     rax, [rax+10h]
0x18001fad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fadb  mov     ebx, eax
0x18001fadd  test    eax, eax
0x18001fadf  js      loc_18001F98A
0x18001fae5  jmp     loc_18001F908
```
