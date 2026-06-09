# CMsftDiscRecorder2::GetTrackInformation(ulong,_IMAPI_READ_TRACK_ADDRESS_TYPE,uchar * *,ulong *)

- ea: `0x18002a6a0`
- end: `0x18002abae`
- name: `?GetTrackInformation@CMsftDiscRecorder2@@UEAAJKW4_IMAPI_READ_TRACK_ADDRESS_TYPE@@PEAPEAEPEAK@Z`
- size: `1294`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, unsigned int, enum _IMAPI_READ_TRACK_ADDRESS_TYPE, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002fc8`
- `0x1800036f0`
- `0x18000ae3c`
- `0x180014134`
- `0x180016778`
- `0x18002a6a0`
- `0x18002d188`
- `0x18002d220`
- `0x18002d428`
- `0x180049832`
- `0x18004984a`
- `0x180049880`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002ab68`
- `ole32!CoTaskMemFree` at `0x18002ab68`
- `ole32!CoTaskMemAlloc` at `0x18002aab3`
- `ole32!CoTaskMemAlloc` at `0x18002aab3`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::GetTrackInformation(
        CMsftDiscRecorder2 *this,
        unsigned int a2,
        unsigned int a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  signed int v5; // ebx
  int v6; // eax
  PVOID *v11; // rcx
  __int64 v12; // r9
  size_t v13; // r8
  unsigned int v14; // r14d
  void *v15; // rcx
  unsigned int v16; // edx
  void *v17; // rdx
  __int64 v18; // r8
  int *v19; // r9
  int v20; // r9d
  unsigned __int8 *v21; // rax
  unsigned __int8 *v22; // rdi
  const struct _GUID *v23; // r8
  __int64 v25; // [rsp+28h] [rbp-89h]
  unsigned __int8 *v26; // [rsp+30h] [rbp-81h]
  unsigned int v27; // [rsp+38h] [rbp-79h]
  _BYTE v28[32]; // [rsp+70h] [rbp-41h] BYREF
  unsigned int v29; // [rsp+90h] [rbp-21h] BYREF
  struct _SENSE_DATA v30; // [rsp+98h] [rbp-19h] BYREF

  v5 = 0;
  v6 = 0;
  if ( a3 <= 2 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 22), 92, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, a3, a3);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    v5 = -2147024809;
    v6 = -2147024809;
  }
  if ( a4 )
  {
    *a4 = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 188) & 4) != 0 && *((_BYTE *)v11 + 185) >= 3u )
    {
      WPP_SF_(v11[22], 93, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    v5 = -2147467261;
    v6 = -2147467261;
  }
  if ( a5 )
  {
    *a5 = 0;
    if ( v6 >= 0 )
    {
      v12 = *((unsigned int *)this + 58);
      if ( (v12 & 2) == 0 )
      {
        v5 = -2147467259;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            95,
            &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            v12,
            -2147467259);
        }
        goto LABEL_54;
      }
      v13 = *((unsigned int *)this + 56);
      v14 = 0;
      v15 = (void *)*((_QWORD *)this + 27);
      v29 = 0;
      memset_0(v15, 0, v13);
      v16 = *((_DWORD *)this + 56);
      *(_OWORD *)&v28[16] = 0;
      v28[17] = a3 & 3;
      v28[18] = HIBYTE(a2);
      v28[19] = BYTE2(a2);
      v28[20] = BYTE1(a2);
      v28[23] = BYTE1(v16);
      v28[24] = v16;
      v27 = v16;
      v17 = (void *)*((_QWORD *)this + 10);
      v26 = (unsigned __int8 *)*((_QWORD *)this + 27);
      memset(&v30, 0, sizeof(v30));
      v28[16] = 82;
      v28[21] = a2;
      *(_DWORD *)v28 = CMsftDiscRecorder2::SendCommandHelper(
                         (CMsftDiscRecorder2 *)((char *)this - 8),
                         v17,
                         (const union _CDB *)&v28[16],
                         0xAu,
                         &v30,
                         0xAu,
                         v26,
                         v27,
                         &v29,
                         1u);
      v5 = *(_DWORD *)v28;
      if ( *(int *)v28 >= 0 )
      {
        if ( *(_DWORD *)v28 == 11141632 )
        {
          Imapi2Utility::TranslateSenseInfoToHResult(
            (Imapi2Utility *)&v28[16],
            (const union _CDB *)&v30,
            (const struct _SENSE_DATA *)v28,
            v19);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
          {
            v5 = *(_DWORD *)v28;
          }
          else
          {
            v20 = *((_DWORD *)this + 56);
            v5 = *(_DWORD *)v28;
            *(_WORD *)&v28[16] = 18;
            *(_QWORD *)&v28[24] = &v30;
            *(_DWORD *)&v28[18] = 0;
            *(_WORD *)&v28[22] = 0;
            WPP_SF_ddDdDdDDDD_HEX_(
              *((_QWORD *)WPP_GLOBAL_Control + 22),
              v30.AdditionalSenseCode,
              *((_BYTE *)&v30 + 2) & 0xF,
              *(_DWORD *)v28,
              a2,
              a2,
              a3,
              a3,
              v20,
              v20,
              *((_BYTE *)&v30 + 2) & 0xF,
              v30.AdditionalSenseCode,
              v30.AdditionalSenseCodeQualifier,
              (__int64)&v28[16]);
          }
        }
        else
        {
          if ( v29 < 0x18 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
            {
              LODWORD(v25) = a3;
              WPP_SF_dDdDdDdDdD(
                *((_QWORD *)WPP_GLOBAL_Control + 22),
                98,
                &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
                a2,
                a2,
                v25,
                a3,
                *((_DWORD *)this + 56),
                *((_DWORD *)this + 56),
                v29,
                v29,
                24,
                24);
            }
            v5 = -2147467259;
            goto LABEL_54;
          }
          v14 = (*(unsigned __int8 *)(*((_QWORD *)this + 27) + 1LL) | (**((unsigned __int8 **)this + 27) << 8)) + 2;
          if ( v14 > *((_DWORD *)this + 56) )
            v5 = -1062599937;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_dDdDdDd(
          *((_QWORD *)WPP_GLOBAL_Control + 22),
          96,
          v18,
          a2,
          a2,
          a3,
          a3,
          *((_DWORD *)this + 56),
          *((_DWORD *)this + 56),
          *(_DWORD *)v28);
      }
      if ( v5 >= 0 )
      {
        v21 = (unsigned __int8 *)CoTaskMemAlloc(v14);
        v22 = v21;
        if ( v21 )
        {
          memcpy_0(v21, *((const void **)this + 27), v14);
          *a4 = v22;
          *a5 = v14;
          goto LABEL_55;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            99,
            &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            v14,
            v14);
        }
        v5 = -2147024882;
      }
    }
  }
  else
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 188) & 4) != 0 && *((_BYTE *)v11 + 185) >= 3u )
      WPP_SF_(v11[22], 94, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    v5 = -2147467261;
  }
LABEL_54:
  CoTaskMemFree(0);
LABEL_55:
  if ( (v5 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v5, (int)&CLSID_MsftDiscRecorder2, v23);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a6a0  push    rbp
0x18002a6a2  push    rbx
0x18002a6a3  push    rsi
0x18002a6a4  push    rdi
0x18002a6a5  push    r12
0x18002a6a7  push    r13
0x18002a6a9  push    r14
0x18002a6ab  push    r15
0x18002a6ad  lea     rbp, [rsp-17h]
0x18002a6b2  sub     rsp, 0C8h
0x18002a6b9  mov     rax, cs:__security_cookie
0x18002a6c0  xor     rax, rsp
0x18002a6c3  mov     [rbp+4Fh+var_50], rax
0x18002a6c7  mov     r12, [rbp+4Fh+arg_20]
0x18002a6cb  xor     ebx, ebx
0x18002a6cd  xor     eax, eax
0x18002a6cf  mov     r15d, edx
0x18002a6d2  lea     rdx, WPP_GLOBAL_Control
0x18002a6d9  mov     r13, r9
0x18002a6dc  mov     edi, r8d
0x18002a6df  mov     rsi, rcx
0x18002a6e2  mov     r14b, 3
0x18002a6e5  test    r8d, r8d
0x18002a6e8  jz      short loc_18002A749
0x18002a6ea  cmp     r8d, 1
0x18002a6ee  jz      short loc_18002A749
0x18002a6f0  cmp     r8d, 2
0x18002a6f4  jz      short loc_18002A749
0x18002a6f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6fd  cmp     rcx, rdx
0x18002a700  jz      short loc_18002A740
0x18002a702  test    byte ptr [rcx+0BCh], 4
0x18002a709  jz      short loc_18002A740
0x18002a70b  cmp     [rcx+0B9h], r14b
0x18002a712  jb      short loc_18002A740
0x18002a714  mov     rcx, [rcx+0B0h]
0x18002a71b  lea     edx, [rbx+5Ch]
0x18002a71e  mov     dword ptr [rsp+100h+var_E0], r8d
0x18002a723  mov     r9d, r8d
0x18002a726  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002a72d  call    WPP_SF_Dd
0x18002a732  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a739  lea     rdx, WPP_GLOBAL_Control
0x18002a740  mov     ebx, 80070057h
0x18002a745  mov     eax, ebx
0x18002a747  jmp     short loc_18002A750
0x18002a749  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a750  test    r13, r13
0x18002a753  jnz     short loc_18002A79A
0x18002a755  cmp     rcx, rdx
0x18002a758  jz      short loc_18002A791
0x18002a75a  test    byte ptr [rcx+0BCh], 4
0x18002a761  jz      short loc_18002A791
0x18002a763  cmp     [rcx+0B9h], r14b
0x18002a76a  jb      short loc_18002A791
0x18002a76c  mov     rcx, [rcx+0B0h]
0x18002a773  lea     edx, [r13+5Dh]
0x18002a777  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002a77e  call    WPP_SF_
0x18002a783  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a78a  lea     rdx, WPP_GLOBAL_Control
0x18002a791  mov     ebx, 80004003h
0x18002a796  mov     eax, ebx
0x18002a798  jmp     short loc_18002A7A9
0x18002a79a  mov     qword ptr [r13+0], 0
0x18002a7a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7a9  test    r12, r12
0x18002a7ac  jnz     short loc_18002A7E7
0x18002a7ae  cmp     rcx, rdx
0x18002a7b1  jz      short loc_18002A7DD
0x18002a7b3  test    byte ptr [rcx+0BCh], 4
0x18002a7ba  jz      short loc_18002A7DD
0x18002a7bc  cmp     [rcx+0B9h], r14b
0x18002a7c3  jb      short loc_18002A7DD
0x18002a7c5  mov     rcx, [rcx+0B0h]
0x18002a7cc  lea     edx, [r12+5Eh]
0x18002a7d1  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002a7d8  call    WPP_SF_
0x18002a7dd  mov     ebx, 80004003h
0x18002a7e2  jmp     loc_18002AB66
0x18002a7e7  mov     dword ptr [r12], 0
0x18002a7ef  test    eax, eax
0x18002a7f1  js      loc_18002AB66
0x18002a7f7  mov     r9d, [rsi+0E8h]
0x18002a7fe  test    r9b, 2
0x18002a802  jz      loc_18002AB27
0x18002a808  mov     r8d, [rsi+0E0h]; Size
0x18002a80f  xor     r14d, r14d
0x18002a812  mov     rcx, [rsi+0D8h]; void *
0x18002a819  xor     edx, edx; Val
0x18002a81b  mov     [rbp+4Fh+var_70], r14d
0x18002a81f  call    memset_0
0x18002a824  mov     edx, [rsi+0E0h]
0x18002a82a  lea     r9d, [r14+0Ah]; unsigned int
0x18002a82e  xor     eax, eax
0x18002a830  mov     [rsp+100h+var_B8], 1; unsigned __int8
0x18002a835  mov     [rbp+4Fh+var_58], ax
0x18002a839  lea     r8, [rbp+4Fh+var_90+10h]; union _CDB *
0x18002a83d  mov     al, dil
0x18002a840  lea     rcx, [rsi-8]; this
0x18002a844  and     al, 3
0x18002a846  xorps   xmm0, xmm0
0x18002a849  movups  xmmword ptr [rbp+4Fh+var_90+10h], xmm0
0x18002a84d  mov     [rbp+4Fh+var_90+11h], al
0x18002a850  mov     eax, r15d
0x18002a853  shr     eax, 18h
0x18002a856  xorps   xmm1, xmm1
0x18002a859  mov     [rbp+4Fh+var_90+12h], al
0x18002a85c  mov     eax, r15d
0x18002a85f  shr     eax, 10h
0x18002a862  mov     [rbp+4Fh+var_90+13h], al
0x18002a865  mov     eax, r15d
0x18002a868  shr     eax, 8
0x18002a86b  mov     [rbp+4Fh+var_90+14h], al
0x18002a86e  mov     eax, edx
0x18002a870  shr     eax, 8
0x18002a873  mov     [rbp+4Fh+var_90+17h], al
0x18002a876  mov     al, dl
0x18002a878  lea     rax, [rbp+4Fh+var_70]
0x18002a87c  mov     [rbp+4Fh+var_90+18h], dl
0x18002a87f  mov     [rsp+100h+var_C0], rax; unsigned int *
0x18002a884  mov     rax, [rsi+0D8h]
0x18002a88b  mov     [rsp+100h+var_C8], edx; unsigned int
0x18002a88f  mov     rdx, [rsi+50h]; void *
0x18002a893  mov     [rsp+100h+var_D0], rax; unsigned __int8 *
0x18002a898  lea     rax, [rbp+4Fh+var_68]
0x18002a89c  mov     dword ptr [rsp+100h+var_D8], r9d; unsigned int
0x18002a8a1  mov     [rsp+100h+var_E0], rax; struct _SENSE_DATA *
0x18002a8a6  movups  xmmword ptr [rbp+4Fh+var_68], xmm1
0x18002a8aa  mov     [rbp+4Fh+var_90+10h], 52h ; 'R'
0x18002a8ae  mov     [rbp+4Fh+var_90+15h], r15b
0x18002a8b2  call    ?SendCommandHelper@CMsftDiscRecorder2@@AEAA?BJQEAXPEBT_CDB@@KPEAU_SENSE_DATA@@KPEAEKPEAKE@Z; CMsftDiscRecorder2::SendCommandHelper(void * const,_CDB const *,ulong,_SENSE_DATA *,ulong,uchar *,ulong,ulong *,uchar)
0x18002a8b7  mov     dword ptr [rbp+4Fh+var_90], eax
0x18002a8ba  mov     ebx, eax
0x18002a8bc  test    eax, eax
0x18002a8be  jns     short loc_18002A928
0x18002a8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8c7  lea     rax, WPP_GLOBAL_Control
0x18002a8ce  cmp     rcx, rax
0x18002a8d1  jz      loc_18002AAA5
0x18002a8d7  test    byte ptr [rcx+0BCh], 4
0x18002a8de  jz      loc_18002AAA5
0x18002a8e4  cmp     byte ptr [rcx+0B9h], 3
0x18002a8eb  jb      loc_18002AAA5
0x18002a8f1  mov     eax, [rsi+0E0h]
0x18002a8f7  lea     edx, [r14+60h]
0x18002a8fb  mov     rcx, [rcx+0B0h]
0x18002a902  mov     r9d, r15d
0x18002a905  mov     dword ptr [rsp+100h+var_B8], ebx
0x18002a909  mov     dword ptr [rsp+100h+var_C0], eax
0x18002a90d  mov     [rsp+100h+var_C8], eax
0x18002a911  mov     dword ptr [rsp+100h+var_D0], edi
0x18002a915  mov     dword ptr [rsp+100h+var_D8], edi
0x18002a919  mov     dword ptr [rsp+100h+var_E0], r15d
0x18002a91e  call    WPP_SF_dDdDdDd
0x18002a923  jmp     loc_18002AAA5
0x18002a928  cmp     ebx, 0AA0200h
0x18002a92e  jnz     loc_18002A9F5
0x18002a934  lea     r8, [rbp+4Fh+var_90]; struct _SENSE_DATA *
0x18002a938  lea     rdx, [rbp+4Fh+var_68]; union _CDB *
0x18002a93c  lea     rcx, [rbp+4Fh+var_90+10h]; this
0x18002a940  call    ?TranslateSenseInfoToHResult@Imapi2Utility@@YA?BEPEBT_CDB@@PEBU_SENSE_DATA@@PEAJ@Z; Imapi2Utility::TranslateSenseInfoToHResult(_CDB const *,_SENSE_DATA const *,long *)
0x18002a945  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a94c  lea     rax, WPP_GLOBAL_Control
0x18002a953  cmp     rcx, rax
0x18002a956  jz      loc_18002A9ED
0x18002a95c  test    byte ptr [rcx+0BCh], 4
0x18002a963  jz      loc_18002A9ED
0x18002a969  cmp     byte ptr [rcx+0B9h], 3
0x18002a970  jb      short loc_18002A9ED
0x18002a972  mov     r9d, [rsi+0E0h]
0x18002a979  lea     r10, [rbp+4Fh+var_90+10h]
0x18002a97d  movzx   r8d, byte ptr [rbp+4Fh+var_68+2]
0x18002a982  xor     edx, edx
0x18002a984  mov     ebx, dword ptr [rbp+4Fh+var_90]
0x18002a987  mov     eax, 12h
0x18002a98c  mov     [rsp+100h+var_98], r10
0x18002a991  and     r8d, 0Fh
0x18002a995  mov     word ptr [rbp+4Fh+var_90+10h], ax
0x18002a999  lea     rax, [rbp+4Fh+var_68]
0x18002a99d  mov     qword ptr [rbp+4Fh+var_90+18h], rax
0x18002a9a1  movzx   eax, byte ptr [rbp+4Fh+var_68+0Dh]
0x18002a9a5  mov     [rsp+100h+var_A0], eax
0x18002a9a9  mov     dword ptr [rbp+4Fh+var_90+12h], edx
0x18002a9ac  mov     word ptr [rbp+4Fh+var_90+16h], dx
0x18002a9b0  movzx   edx, byte ptr [rbp+4Fh+var_68+0Ch]
0x18002a9b4  mov     rcx, [rcx+0B0h]
0x18002a9bb  mov     [rsp+100h+var_A8], edx
0x18002a9bf  mov     [rsp+100h+var_B0], r8d
0x18002a9c4  mov     dword ptr [rsp+100h+var_B8], r9d
0x18002a9c9  mov     dword ptr [rsp+100h+var_C0], r9d
0x18002a9ce  mov     r9d, ebx
0x18002a9d1  mov     [rsp+100h+var_C8], edi
0x18002a9d5  mov     dword ptr [rsp+100h+var_D0], edi
0x18002a9d9  mov     dword ptr [rsp+100h+var_D8], r15d
0x18002a9de  mov     dword ptr [rsp+100h+var_E0], r15d
0x18002a9e3  call    WPP_SF_ddDdDdDDDD_HEX_
0x18002a9e8  jmp     loc_18002AAA5
0x18002a9ed  mov     ebx, dword ptr [rbp+4Fh+var_90]
0x18002a9f0  jmp     loc_18002AAA5
0x18002a9f5  mov     r8d, [rbp+4Fh+var_70]
0x18002a9f9  mov     r9d, 18h
0x18002a9ff  cmp     r8d, r9d
0x18002aa02  jnb     short loc_18002AA7C
0x18002aa04  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa0b  lea     rax, WPP_GLOBAL_Control
0x18002aa12  cmp     rcx, rax
0x18002aa15  jz      short loc_18002AA72
0x18002aa17  test    byte ptr [rcx+0BCh], 4
0x18002aa1e  jz      short loc_18002AA72
0x18002aa20  cmp     byte ptr [rcx+0B9h], 3
0x18002aa27  jb      short loc_18002AA72
0x18002aa29  mov     eax, [rsi+0E0h]
0x18002aa2f  lea     edx, [r9+4Ah]
0x18002aa33  mov     rcx, [rcx+0B0h]
0x18002aa3a  mov     [rsp+100h+var_A0], r9d
0x18002aa3f  mov     [rsp+100h+var_A8], r9d
0x18002aa44  mov     r9d, r15d
0x18002aa47  mov     [rsp+100h+var_B0], r8d
0x18002aa4c  mov     dword ptr [rsp+100h+var_B8], r8d
0x18002aa51  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002aa58  mov     dword ptr [rsp+100h+var_C0], eax
0x18002aa5c  mov     [rsp+100h+var_C8], eax
0x18002aa60  mov     dword ptr [rsp+100h+var_D0], edi
0x18002aa64  mov     dword ptr [rsp+100h+var_D8], edi
0x18002aa68  mov     dword ptr [rsp+100h+var_E0], r15d
0x18002aa6d  call    WPP_SF_dDdDdDdDdD
0x18002aa72  mov     ebx, 80004005h
0x18002aa77  jmp     loc_18002AB66
0x18002aa7c  mov     rax, [rsi+0D8h]
0x18002aa83  movzx   r14d, byte ptr [rax]
0x18002aa87  movzx   eax, byte ptr [rax+1]
0x18002aa8b  shl     r14d, 8
0x18002aa8f  or      r14d, eax
0x18002aa92  mov     eax, 0C0AA02FFh
0x18002aa97  add     r14d, 2
0x18002aa9b  cmp     r14d, [rsi+0E0h]
0x18002aaa2  cmova   ebx, eax
0x18002aaa5  test    ebx, ebx
0x18002aaa7  js      loc_18002AB66
0x18002aaad  mov     ecx, r14d; cb
0x18002aab0  mov     r15d, r14d
0x18002aab3  call    cs:__imp_CoTaskMemAlloc
0x18002aab9  mov     rdi, rax
0x18002aabc  test    rax, rax
0x18002aabf  jnz     short loc_18002AB0B
0x18002aac1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aac8  lea     rax, WPP_GLOBAL_Control
0x18002aacf  cmp     rcx, rax
0x18002aad2  jz      short loc_18002AB04
0x18002aad4  test    byte ptr [rcx+0BCh], 4
0x18002aadb  jz      short loc_18002AB04
0x18002aadd  cmp     byte ptr [rcx+0B9h], 3
0x18002aae4  jb      short loc_18002AB04
0x18002aae6  mov     rcx, [rcx+0B0h]
0x18002aaed  lea     edx, [rdi+63h]
0x18002aaf0  mov     r9d, r14d
0x18002aaf3  mov     dword ptr [rsp+100h+var_E0], r14d
0x18002aaf8  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002aaff  call    WPP_SF_Dd
0x18002ab04  mov     ebx, 8007000Eh
0x18002ab09  jmp     short loc_18002AB66
0x18002ab0b  mov     rdx, [rsi+0D8h]; Src
0x18002ab12  mov     r8, r15; Size
0x18002ab15  mov     rcx, rdi; void *
0x18002ab18  call    memcpy_0
0x18002ab1d  mov     [r13+0], rdi
0x18002ab21  mov     [r12], r14d
0x18002ab25  jmp     short loc_18002AB6E
0x18002ab27  mov     ebx, 80004005h
0x18002ab2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab33  cmp     rcx, rdx
0x18002ab36  jz      short loc_18002AB66
0x18002ab38  test    byte ptr [rcx+0BCh], 4
0x18002ab3f  jz      short loc_18002AB66
0x18002ab41  cmp     [rcx+0B9h], r14b
0x18002ab48  jb      short loc_18002AB66
0x18002ab4a  mov     rcx, [rcx+0B0h]
0x18002ab51  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002ab58  mov     edx, 5Fh ; '_'
0x18002ab5d  mov     dword ptr [rsp+100h+var_E0], ebx
0x18002ab61  call    WPP_SF_Dd
0x18002ab66  xor     ecx, ecx; pv
0x18002ab68  call    cs:__imp_CoTaskMemFree
0x18002ab6e  mov     ecx, ebx
0x18002ab70  and     ecx, 80FF0000h
0x18002ab76  cmp     ecx, 80AA0000h
0x18002ab7c  jnz     short loc_18002AB8C
0x18002ab7e  lea     rdx, CLSID_MsftDiscRecorder2; int
0x18002ab85  mov     ecx, ebx; dwMessageId
0x18002ab87  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18002ab8c  mov     eax, ebx
0x18002ab8e  mov     rcx, [rbp+4Fh+var_50]
0x18002ab92  xor     rcx, rsp; StackCookie
0x18002ab95  call    __security_check_cookie
0x18002ab9a  add     rsp, 0C8h
0x18002aba1  pop     r15
0x18002aba3  pop     r14
0x18002aba5  pop     r13
0x18002aba7  pop     r12
  ... truncated ...
```
