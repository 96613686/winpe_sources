# CLTLegacyClasses::GetTable(_GUID const &,_GUID const &,void *,void *,ulong,ulong,void *,void * *)

- ea: `0x18001aea0`
- end: `0x18001b378`
- name: `?GetTable@CLTLegacyClasses@@UEAAJAEBU_GUID@@0PEAX1KK1PEAPEAX@Z`
- size: `1240`
- prototype: `__int64 __fastcall(CLTLegacyClasses *__hidden this, const struct _GUID *, const struct _GUID *, void *, void *, unsigned int, unsigned int, void *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18001aea0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001af95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001af95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b2e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b2e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b0d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b0d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTLegacyClasses::GetTable(
        CLTLegacyClasses *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        _QWORD *a4,
        void *a5,
        unsigned int a6,
        unsigned int a7,
        void *a8,
        void **a9)
{
  HRESULT v10; // ebx
  unsigned int i; // edx
  __int64 v12; // rax
  __int64 v13; // rcx
  _DWORD *v14; // r15
  unsigned int j; // r12d
  __int64 v16; // rsi
  unsigned int v17; // ecx
  void *v18; // rcx
  __int64 v20; // [rsp+58h] [rbp-29h] BYREF
  __int64 v21; // [rsp+60h] [rbp-21h] BYREF
  __int64 v22; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v23[10]; // [rsp+70h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+E8h] [rbp+67h] BYREF

  ppv = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23[0] = 0;
  if ( a6 == 1 )
  {
    *((_DWORD *)this + 70) = 0;
    for ( i = 0; i < (unsigned int)a5; ++i )
    {
      v12 = HIDWORD(a4[3 * i + 1]);
      if ( (_DWORD)v12 != -268435454 )
      {
        if ( (unsigned int)v12 >= 0x18
          || *((_DWORD *)&g_aMetaHelper + 3 * v12) != 1
          || !a4[3 * i]
          || LODWORD(a4[3 * i + 1]) )
        {
          v10 = -2147024809;
          goto LABEL_41;
        }
        v13 = 3LL * *((unsigned int *)this + 70);
        *(_OWORD *)((char *)this + 8 * v13 + 40) = *(_OWORD *)&a4[3 * i];
        *((_QWORD *)this + v13 + 7) = a4[3 * i + 2];
        *((_DWORD *)this + 6 * (unsigned int)(*((_DWORD *)this + 70))++ + 13) = *((_DWORD *)&g_aMetaHelper + 3 * v12 + 1);
      }
    }
    v10 = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64 *, _GUID **, __int64, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
              ppv,
              &didCOMSERVICES,
              tidMETA,
              &off_18005B9F0,
              1,
              1,
              3,
              &v22);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 32LL))(v22);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, __int64 (**)[2], __int64, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                  ppv,
                  didCOMCLASSIC,
                  tidMETA,
                  &off_18005BA20,
                  1,
                  1,
                  3,
                  &v20);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 32LL))(v20);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, __int64 (**)[2], __int64, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                      ppv,
                      didCOMCLASSIC,
                      tidMETA,
                      &off_18005BA08,
                      1,
                      1,
                      3,
                      &v21);
              if ( v10 >= 0 )
              {
                v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 32LL))(v21);
                if ( v10 >= 0 )
                {
                  *((_DWORD *)this + 5) = 24;
                  v14 = CoTaskMemAlloc(0x120u);
                  if ( v14 )
                  {
                    for ( j = 0; j < *((_DWORD *)this + 5); ++j )
                    {
                      switch ( *((_DWORD *)&g_aMetaHelper + 3 * j) )
                      {
                        case 1:
                          v16 = v22;
                          break;
                        case 2:
                          v16 = v20;
                          break;
                        case 3:
                          v16 = v21;
                          break;
                        default:
                          v10 = -2147418113;
                          goto LABEL_40;
                      }
                      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 48LL))(
                              v16,
                              *((unsigned int *)&g_aMetaHelper + 3 * j + 1));
                      if ( v10 < 0 )
                        goto LABEL_40;
                      v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, 1, 0);
                      if ( v10 < 0 )
                        goto LABEL_40;
                      v14[3 * j] = MEMORY[0];
                      v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, 2, 0);
                      if ( v10 < 0 )
                        goto LABEL_40;
                      v14[3 * j + 1] = MEMORY[0];
                      v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, 3, 0);
                      if ( v10 < 0 )
                        goto LABEL_40;
                      v17 = MEMORY[0] & 0xFFFFFFFE;
                      v14[3 * j + 2] = MEMORY[0] & 0xFFFFFFFE;
                      v14[3 * j + 2] = *((_DWORD *)&g_aMetaHelper + 3 * j + 2) | v17;
                    }
                    v10 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, _QWORD, _QWORD, int, int, char *))(*(_QWORD *)ppv + 24LL))(
                            ppv,
                            didMEMORY,
                            tidMEMORY_SHAPEABLE,
                            0,
                            0,
                            1,
                            8,
                            (char *)this + 24);
                    if ( v10 >= 0 )
                    {
                      v10 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))this + 3))(
                              *((_QWORD *)this + 3),
                              &IID_ISimpleTableControl,
                              v23);
                      if ( v10 >= 0 )
                      {
                        v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _DWORD *))(*(_QWORD *)v23[0] + 24LL))(
                                v23[0],
                                8,
                                *((unsigned int *)this + 5),
                                v14);
                        if ( v10 >= 0 )
                        {
                          *((_DWORD *)this + 4) = a7;
                          v18 = (void *)(((unsigned __int64)this - 16) & -(__int64)(this != (CLTLegacyClasses *)24));
                          *a9 = v18;
                          (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 8LL))(v18);
                          _InterlockedAdd((volatile signed __int32 *)this + 3, 1u);
                          *((_QWORD *)this + 4) = ppv;
                          ppv = 0;
                        }
                      }
                    }
LABEL_40:
                    CoTaskMemFree(v14);
                  }
                  else
                  {
                    v10 = -2147024882;
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_41:
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
    if ( v20 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v20 = 0;
    }
    if ( v21 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v21 = 0;
    }
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v22 = 0;
    }
    if ( v23[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 16LL))(v23[0]);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001aea0  push    rbp
0x18001aea2  push    rbx
0x18001aea3  push    rsi
0x18001aea4  push    rdi
0x18001aea5  push    r12
0x18001aea7  push    r13
0x18001aea9  push    r14
0x18001aeab  push    r15
0x18001aead  lea     rbp, [rsp-7]
0x18001aeb2  sub     rsp, 88h
0x18001aeb9  mov     rdi, rcx
0x18001aebc  xor     r13d, r13d
0x18001aebf  mov     [rbp+3Fh+arg_18], r13
0x18001aec3  mov     [rbp+3Fh+var_68], r13
0x18001aec7  mov     [rbp+3Fh+var_60], r13
0x18001aecb  mov     [rbp+3Fh+var_58], r13
0x18001aecf  mov     [rbp+3Fh+var_50], r13
0x18001aed3  mov     [rbp+3Fh+var_70], r13
0x18001aed7  lea     r14d, [r13+1]
0x18001aedb  cmp     [rbp+3Fh+arg_28], r14d
0x18001aedf  jz      short loc_18001AEEB
0x18001aee1  mov     ebx, 80070057h
0x18001aee6  jmp     loc_18001B362
0x18001aeeb  mov     [rcx+118h], r13d
0x18001aef2  mov     edx, r13d
0x18001aef5  lea     rsi, ?g_aMetaHelper@@3PAU_META_HELPER@@A; _META_HELPER near * g_aMetaHelper
0x18001aefc  cmp     edx, dword ptr [rbp+3Fh+arg_20]
0x18001aeff  jnb     short loc_18001AF79
0x18001af01  mov     eax, edx
0x18001af03  lea     r8, [rax+rax*2]
0x18001af07  mov     eax, [r9+r8*8+0Ch]
0x18001af0c  cmp     eax, 0F0000002h
0x18001af11  jz      short loc_18001AF6A
0x18001af13  cmp     eax, 18h
0x18001af16  jnb     short loc_18001AF6F
0x18001af18  lea     r10, [rax+rax*2]
0x18001af1c  cmp     [rsi+r10*4], r14d
0x18001af20  jnz     short loc_18001AF6F
0x18001af22  cmp     [r9+r8*8], r13
0x18001af26  jz      short loc_18001AF6F
0x18001af28  cmp     [r9+r8*8+8], r13d
0x18001af2d  jnz     short loc_18001AF6F
0x18001af2f  mov     eax, [rdi+118h]
0x18001af35  lea     rcx, [rax+rax*2]
0x18001af39  movups  xmm0, xmmword ptr [r9+r8*8]
0x18001af3e  movups  xmmword ptr [rdi+rcx*8+28h], xmm0
0x18001af43  movsd   xmm1, qword ptr [r9+r8*8+10h]
0x18001af4a  movsd   qword ptr [rdi+rcx*8+38h], xmm1
0x18001af50  mov     eax, [rdi+118h]
0x18001af56  lea     rcx, [rax+rax*2]
0x18001af5a  mov     eax, [rsi+r10*4+4]
0x18001af5f  mov     [rdi+rcx*8+34h], eax
0x18001af63  add     [rdi+118h], r14d
0x18001af6a  add     edx, r14d
0x18001af6d  jmp     short loc_18001AEFC
0x18001af6f  mov     ebx, 80070057h
0x18001af74  jmp     loc_18001B2E9
0x18001af79  lea     rax, [rbp+3Fh+arg_18]
0x18001af7d  mov     [rsp+0C0h+ppv], rax; ppv
0x18001af82  lea     r9, IID_ISimpleTableDispenser; riid
0x18001af89  mov     r8d, r14d; dwClsContext
0x18001af8c  xor     edx, edx; pUnkOuter
0x18001af8e  lea     rcx, CLSID_STDispenser; rclsid
0x18001af95  call    cs:__imp_CoCreateInstance
0x18001af9b  mov     ebx, eax
0x18001af9d  test    eax, eax
0x18001af9f  js      loc_18001B2E9
0x18001afa5  mov     rcx, [rbp+3Fh+arg_18]
0x18001afa9  mov     rax, [rcx]
0x18001afac  lea     rdx, [rbp+3Fh+var_58]
0x18001afb0  mov     [rsp+0C0h+var_88], rdx
0x18001afb5  mov     r12d, 3
0x18001afbb  mov     [rsp+0C0h+var_90], r12d
0x18001afc0  mov     [rsp+0C0h+var_98], r14d
0x18001afc5  mov     [rsp+0C0h+ppv], r14
0x18001afca  lea     r9, off_18005B9F0
0x18001afd1  lea     r15, tidMETA
0x18001afd8  mov     r8, r15
0x18001afdb  lea     rdx, didCOMSERVICES
0x18001afe2  mov     rax, [rax+18h]
0x18001afe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afeb  mov     ebx, eax
0x18001afed  test    eax, eax
0x18001afef  js      loc_18001B2E9
0x18001aff5  mov     rcx, [rbp+3Fh+var_58]
0x18001aff9  mov     rax, [rcx]
0x18001affc  mov     rax, [rax+20h]
0x18001b000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b005  mov     ebx, eax
0x18001b007  test    eax, eax
0x18001b009  js      loc_18001B2E9
0x18001b00f  mov     rcx, [rbp+3Fh+arg_18]
0x18001b013  mov     rax, [rcx]
0x18001b016  lea     rdx, [rbp+3Fh+var_68]
0x18001b01a  mov     [rsp+0C0h+var_88], rdx
0x18001b01f  mov     [rsp+0C0h+var_90], r12d
0x18001b024  mov     [rsp+0C0h+var_98], r14d
0x18001b029  mov     [rsp+0C0h+ppv], r14
0x18001b02e  lea     r9, off_18005BA20
0x18001b035  mov     r8, r15
0x18001b038  lea     rdx, didCOMCLASSIC
0x18001b03f  mov     rax, [rax+18h]
0x18001b043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b048  mov     ebx, eax
0x18001b04a  test    eax, eax
0x18001b04c  js      loc_18001B2E9
0x18001b052  mov     rcx, [rbp+3Fh+var_68]
0x18001b056  mov     rax, [rcx]
0x18001b059  mov     rax, [rax+20h]
0x18001b05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b062  mov     ebx, eax
0x18001b064  test    eax, eax
0x18001b066  js      loc_18001B2E9
0x18001b06c  mov     rcx, [rbp+3Fh+arg_18]
0x18001b070  mov     rax, [rcx]
0x18001b073  lea     r9, [rbp+3Fh+var_60]
0x18001b077  mov     [rsp+0C0h+var_88], r9
0x18001b07c  mov     [rsp+0C0h+var_90], r12d
0x18001b081  mov     [rsp+0C0h+var_98], r14d
0x18001b086  mov     [rsp+0C0h+ppv], r14
0x18001b08b  lea     r9, off_18005BA08
0x18001b092  mov     r8, r15
0x18001b095  lea     rdx, didCOMCLASSIC
0x18001b09c  mov     rax, [rax+18h]
0x18001b0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0a5  mov     ebx, eax
0x18001b0a7  test    eax, eax
0x18001b0a9  js      loc_18001B2E9
0x18001b0af  mov     rcx, [rbp+3Fh+var_60]
0x18001b0b3  mov     rax, [rcx]
0x18001b0b6  mov     rax, [rax+20h]
0x18001b0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0bf  mov     ebx, eax
0x18001b0c1  test    eax, eax
0x18001b0c3  js      loc_18001B2E9
0x18001b0c9  mov     dword ptr [rdi+14h], 18h
0x18001b0d0  mov     ecx, 120h; cb
0x18001b0d5  call    cs:__imp_CoTaskMemAlloc
0x18001b0db  mov     r15, rax
0x18001b0de  test    rax, rax
0x18001b0e1  jnz     short loc_18001B0ED
0x18001b0e3  mov     ebx, 8007000Eh
0x18001b0e8  jmp     loc_18001B2E9
0x18001b0ed  mov     r12d, r13d
0x18001b0f0  cmp     r12d, [rdi+14h]
0x18001b0f4  jnb     loc_18001B21D
0x18001b0fa  mov     eax, r12d
0x18001b0fd  lea     r14, [rax+rax*2]
0x18001b101  mov     ecx, [rsi+r14*4]
0x18001b105  sub     ecx, 1
0x18001b108  jz      short loc_18001B124
0x18001b10a  sub     ecx, 1
0x18001b10d  jz      short loc_18001B11E
0x18001b10f  cmp     ecx, 1
0x18001b112  jnz     loc_18001B213
0x18001b118  mov     rsi, [rbp+3Fh+var_60]
0x18001b11c  jmp     short loc_18001B128
0x18001b11e  mov     rsi, [rbp+3Fh+var_68]
0x18001b122  jmp     short loc_18001B128
0x18001b124  mov     rsi, [rbp+3Fh+var_58]
0x18001b128  mov     rax, [rsi]
0x18001b12b  lea     rdx, ?g_aMetaHelper@@3PAU_META_HELPER@@A; _META_HELPER near * g_aMetaHelper
0x18001b132  mov     edx, [rdx+r14*4+4]
0x18001b137  mov     rcx, rsi
0x18001b13a  mov     rax, [rax+30h]
0x18001b13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b143  mov     ebx, eax
0x18001b145  test    eax, eax
0x18001b147  js      loc_18001B2DF
0x18001b14d  mov     rax, [rsi]
0x18001b150  lea     rcx, [rbp+3Fh+var_70]
0x18001b154  mov     [rsp+0C0h+ppv], rcx
0x18001b159  xor     r9d, r9d
0x18001b15c  xor     r8d, r8d
0x18001b15f  lea     edx, [r9+1]
0x18001b163  mov     rcx, rsi
0x18001b166  mov     rax, [rax+40h]
0x18001b16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b16f  mov     ebx, eax
0x18001b171  test    eax, eax
0x18001b173  js      loc_18001B2DF
0x18001b179  mov     rax, [rbp+3Fh+var_70]
0x18001b17d  mov     ecx, [rax]
0x18001b17f  mov     [r15+r14*4], ecx
0x18001b183  mov     rax, [rsi]
0x18001b186  lea     rcx, [rbp+3Fh+var_70]
0x18001b18a  mov     [rsp+0C0h+ppv], rcx
0x18001b18f  xor     r9d, r9d
0x18001b192  xor     r8d, r8d
0x18001b195  lea     edx, [r9+2]
0x18001b199  mov     rcx, rsi
0x18001b19c  mov     rax, [rax+40h]
0x18001b1a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1a5  mov     ebx, eax
0x18001b1a7  test    eax, eax
0x18001b1a9  js      loc_18001B2DF
0x18001b1af  mov     rax, [rbp+3Fh+var_70]
0x18001b1b3  mov     edx, [rax]
0x18001b1b5  mov     [r15+r14*4+4], edx
0x18001b1ba  mov     rax, [rsi]
0x18001b1bd  lea     rcx, [rbp+3Fh+var_70]
0x18001b1c1  mov     [rsp+0C0h+ppv], rcx
0x18001b1c6  xor     r9d, r9d
0x18001b1c9  xor     r8d, r8d
0x18001b1cc  lea     edx, [r9+3]
0x18001b1d0  mov     rcx, rsi
0x18001b1d3  mov     rax, [rax+40h]
0x18001b1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1dc  mov     ebx, eax
0x18001b1de  test    eax, eax
0x18001b1e0  js      loc_18001B2DF
0x18001b1e6  mov     rax, [rbp+3Fh+var_70]
0x18001b1ea  mov     ecx, [rax]
0x18001b1ec  and     ecx, 0FFFFFFFEh
0x18001b1ef  mov     [r15+r14*4+8], ecx
0x18001b1f4  lea     rsi, ?g_aMetaHelper@@3PAU_META_HELPER@@A; _META_HELPER near * g_aMetaHelper
0x18001b1fb  or      ecx, [rsi+r14*4+8]
0x18001b200  mov     [r15+r14*4+8], ecx
0x18001b205  mov     r14d, 1
0x18001b20b  add     r12d, r14d
0x18001b20e  jmp     loc_18001B0F0
0x18001b213  mov     ebx, 8000FFFFh
0x18001b218  jmp     loc_18001B2DF
0x18001b21d  lea     rsi, [rdi+18h]
0x18001b221  mov     rcx, [rbp+3Fh+arg_18]
0x18001b225  mov     rax, [rcx]
0x18001b228  mov     [rsp+0C0h+var_88], rsi
0x18001b22d  mov     r12d, 8
0x18001b233  mov     [rsp+0C0h+var_90], r12d
0x18001b238  mov     [rsp+0C0h+var_98], r14d
0x18001b23d  mov     [rsp+0C0h+ppv], r13
0x18001b242  xor     r9d, r9d
0x18001b245  lea     r8, tidMEMORY_SHAPEABLE
0x18001b24c  lea     rdx, didMEMORY
0x18001b253  mov     rax, [rax+18h]
0x18001b257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b25c  mov     ebx, eax
0x18001b25e  test    eax, eax
0x18001b260  js      short loc_18001B2DF
0x18001b262  mov     rcx, [rsi]
0x18001b265  mov     rax, [rcx]
0x18001b268  lea     r8, [rbp+3Fh+var_50]
0x18001b26c  lea     rdx, IID_ISimpleTableControl
0x18001b273  mov     rax, [rax]
0x18001b276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b27b  mov     ebx, eax
0x18001b27d  test    eax, eax
0x18001b27f  js      short loc_18001B2DF
0x18001b281  mov     rcx, [rbp+3Fh+var_50]
0x18001b285  mov     rax, [rcx]
0x18001b288  mov     r9, r15
0x18001b28b  mov     r8d, [rdi+14h]
0x18001b28f  mov     edx, r12d
0x18001b292  mov     rax, [rax+18h]
0x18001b296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b29b  mov     ebx, eax
0x18001b29d  test    eax, eax
0x18001b29f  js      short loc_18001B2DF
0x18001b2a1  mov     eax, [rbp+3Fh+arg_30]
0x18001b2a4  mov     [rdi+10h], eax
0x18001b2a7  lea     rax, [rdi-18h]
0x18001b2ab  lea     rdx, [rdi-10h]
0x18001b2af  neg     rax
0x18001b2b2  sbb     rcx, rcx
0x18001b2b5  and     rcx, rdx
0x18001b2b8  mov     rax, [rbp+3Fh+arg_40]
0x18001b2bf  mov     [rax], rcx
0x18001b2c2  mov     rax, [rcx]
0x18001b2c5  mov     rax, [rax+8]
0x18001b2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2ce  lock add [rdi+0Ch], r14d
0x18001b2d3  mov     rax, [rbp+3Fh+arg_18]
0x18001b2d7  mov     [rdi+20h], rax
0x18001b2db  mov     [rbp+3Fh+arg_18], r13
0x18001b2df  mov     rcx, r15; pv
0x18001b2e2  call    cs:__imp_CoTaskMemFree
0x18001b2e8  nop
0x18001b2e9  mov     rcx, [rbp+3Fh+arg_18]
0x18001b2ed  test    rcx, rcx
0x18001b2f0  jz      short loc_18001B302
0x18001b2f2  mov     rax, [rcx]
0x18001b2f5  mov     rax, [rax+10h]
0x18001b2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2fe  mov     [rbp+3Fh+arg_18], r13
0x18001b302  mov     rcx, [rbp+3Fh+var_68]
0x18001b306  test    rcx, rcx
0x18001b309  jz      short loc_18001B31B
0x18001b30b  mov     rax, [rcx]
0x18001b30e  mov     rax, [rax+10h]
0x18001b312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b317  mov     [rbp+3Fh+var_68], r13
0x18001b31b  mov     rcx, [rbp+3Fh+var_60]
0x18001b31f  test    rcx, rcx
0x18001b322  jz      short loc_18001B334
0x18001b324  mov     rax, [rcx]
0x18001b327  mov     rax, [rax+10h]
0x18001b32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b330  mov     [rbp+3Fh+var_60], r13
0x18001b334  mov     rcx, [rbp+3Fh+var_58]
0x18001b338  test    rcx, rcx
  ... truncated ...
```
