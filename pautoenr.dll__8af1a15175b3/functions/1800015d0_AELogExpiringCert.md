# AELogExpiringCert

- ea: `0x1800015d0`
- end: `0x180001a59`
- name: `AELogExpiringCert`
- size: `1161`
- prototype: `int __fastcall(__int64, const CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001d90`

## callees

- `0x1800015d0`
- `0x1800027e0`
- `0x180007d20`

## import_xrefs

- `CRYPT32!CertGetCertificateContextProperty` at `0x180001636`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180001636`

## pseudocode

```c
int __fastcall AELogExpiringCert(__int64 a1, const CERT_CONTEXT *a2)
{
  unsigned int i; // edi
  __int64 v3; // r11
  __int16 v4; // dx
  unsigned __int8 v5; // r9
  unsigned int v6; // r8d
  unsigned int v7; // ecx
  __int16 v8; // r8
  __int16 v9; // r8
  unsigned __int8 v10; // r9
  unsigned int v11; // edx
  __int16 v12; // r8
  unsigned int v13; // ecx
  unsigned __int8 v14; // r10
  __int16 v15; // r8
  unsigned int v16; // edx
  __int64 v17; // r9
  __int16 v18; // r8
  unsigned int v19; // ecx
  unsigned __int8 v20; // r10
  __int16 v21; // r8
  unsigned int v22; // edx
  __int16 v23; // r8
  unsigned int v24; // ecx
  unsigned __int8 v25; // r10
  __int16 v26; // r8
  unsigned int v27; // edx
  __int64 v28; // r9
  __int16 v29; // r8
  unsigned int v30; // ecx
  unsigned __int8 v31; // r10
  __int16 v32; // r8
  unsigned int v33; // edx
  __int64 v34; // rcx
  __int64 v35; // r9
  __int16 v36; // r8
  unsigned int v37; // ecx
  unsigned __int8 v38; // r10
  __int16 v39; // r8
  unsigned int v40; // edx
  __int64 v41; // rcx
  __int64 v42; // r9
  __int16 v43; // r8
  unsigned int v44; // ecx
  unsigned __int8 v45; // r10
  __int16 v46; // r8
  unsigned int v47; // edx
  __int16 v48; // r8
  unsigned int v49; // ecx
  unsigned __int8 v50; // r10
  __int16 v51; // r8
  unsigned int v52; // edx
  __int64 v53; // r9
  __int16 v54; // r8
  unsigned int v55; // ecx
  unsigned __int8 v56; // r10
  __int16 v57; // r8
  unsigned int v58; // edx
  __int16 v59; // r8
  unsigned int v60; // ecx
  DWORD pcbData; // [rsp+40h] [rbp-69h] BYREF
  __int128 pvData; // [rsp+48h] [rbp-61h] BYREF
  int v64; // [rsp+58h] [rbp-51h]
  _OWORD v65[7]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v66; // [rsp+D0h] [rbp+27h]

  pcbData = 20;
  v64 = 0;
  v66 = 0;
  pvData = 0;
  memset(v65, 0, sizeof(v65));
  if ( CertGetCertificateContextProperty(a2, 3u, &pvData, &pcbData) )
  {
    for ( i = 0; i < 0x14; i += 10 )
    {
      v3 = 3 * i;
      v4 = 48;
      v5 = *((_BYTE *)&pvData + i);
      v6 = v5 >> 4;
      if ( v6 > 9 )
        v4 = 87;
      v7 = v5 & 0xF;
      *((_WORD *)v65 + v3) = v6 + v4;
      v8 = 48;
      if ( v7 > 9 )
        v8 = 87;
      *((_WORD *)v65 + (unsigned int)(v3 + 1)) = v7 + v8;
      *((_WORD *)v65 + (unsigned int)(v3 + 2)) = 32;
      v9 = 48;
      v10 = *((_BYTE *)&pvData + i + 1);
      v11 = v10 >> 4;
      if ( v11 > 9 )
        v9 = 87;
      *((_WORD *)v65 + (unsigned int)(v3 + 3)) = v11 + v9;
      v12 = 48;
      v13 = v10 & 0xF;
      v14 = *((_BYTE *)&pvData + i + 2);
      if ( v13 > 9 )
        v12 = 87;
      *((_WORD *)v65 + (unsigned int)(v3 + 4)) = v13 + v12;
      *((_WORD *)v65 + (unsigned int)(v3 + 5)) = 32;
      v15 = 48;
      v16 = v14 >> 4;
      v17 = i + 3;
      if ( v16 > 9 )
        v15 = 87;
      *((_WORD *)v65 + 3 * i + 6) = v16 + v15;
      v18 = 48;
      v19 = v14 & 0xF;
      v20 = *((_BYTE *)&pvData + v17);
      if ( v19 > 9 )
        v18 = 87;
      *((_WORD *)v65 + (unsigned int)(v3 + 7)) = v19 + v18;
      *((_WORD *)v65 + (unsigned int)(v3 + 8)) = 32;
      v21 = 48;
      v22 = v20 >> 4;
      if ( v22 > 9 )
        v21 = 87;
      *((_WORD *)v65 + (unsigned int)(3 * v17)) = v22 + v21;
      v23 = 48;
      v24 = v20 & 0xF;
      if ( v24 > 9 )
        v23 = 87;
      *((_WORD *)v65 + (unsigned int)(v3 + 10)) = v24 + v23;
      v25 = *((_BYTE *)&pvData + i + 4);
      *((_WORD *)v65 + (unsigned int)(v3 + 11)) = 32;
      v26 = 48;
      v27 = v25 >> 4;
      v28 = i + 5;
      if ( v27 > 9 )
        v26 = 87;
      *((_WORD *)&v65[1] + 3 * i + 4) = v27 + v26;
      v29 = 48;
      v30 = v25 & 0xF;
      v31 = *((_BYTE *)&pvData + v28);
      if ( v30 > 9 )
        v29 = 87;
      *((_WORD *)v65 + (unsigned int)(v3 + 13)) = v30 + v29;
      *((_WORD *)v65 + (unsigned int)(v3 + 14)) = 32;
      v32 = 48;
      v33 = v31 >> 4;
      v34 = (unsigned int)(3 * v28);
      v35 = i + 6;
      if ( v33 > 9 )
        v32 = 87;
      *((_WORD *)v65 + v34) = v33 + v32;
      v36 = 48;
      v37 = v31 & 0xF;
      v38 = *((_BYTE *)&pvData + v35);
      if ( v37 > 9 )
        v36 = 87;
      *((_WORD *)v65 + (unsigned int)(v3 + 16)) = v37 + v36;
      *((_WORD *)v65 + (unsigned int)(v3 + 17)) = 32;
      v39 = 48;
      v40 = v38 >> 4;
      v41 = (unsigned int)(3 * v35);
      v42 = i + 7;
      if ( v40 > 9 )
        v39 = 87;
      *((_WORD *)v65 + v41) = v40 + v39;
      v43 = 48;
      v44 = v38 & 0xF;
      v45 = *((_BYTE *)&pvData + v42);
      if ( v44 > 9 )
        v43 = 87;
      *((_WORD *)v65 + (unsigned int)(v3 + 19)) = v44 + v43;
      *((_WORD *)v65 + (unsigned int)(v3 + 20)) = 32;
      v46 = 48;
      v47 = v45 >> 4;
      if ( v47 > 9 )
        v46 = 87;
      *((_WORD *)v65 + (unsigned int)(3 * v42)) = v47 + v46;
      v48 = 48;
      v49 = v45 & 0xF;
      if ( v49 > 9 )
        v48 = 87;
      v50 = *((_BYTE *)&pvData + i + 8);
      *((_WORD *)v65 + (unsigned int)(v3 + 22)) = v49 + v48;
      *((_WORD *)v65 + (unsigned int)(v3 + 23)) = 32;
      v51 = 48;
      v52 = v50 >> 4;
      v53 = i + 9;
      if ( v52 > 9 )
        v51 = 87;
      *((_WORD *)&v65[3] + 3 * i) = v52 + v51;
      v54 = 48;
      v55 = v50 & 0xF;
      v56 = *((_BYTE *)&pvData + v53);
      if ( v55 > 9 )
        v54 = 87;
      *((_WORD *)v65 + (unsigned int)(v3 + 25)) = v55 + v54;
      *((_WORD *)v65 + (unsigned int)(v3 + 26)) = 32;
      v57 = 48;
      v58 = v56 >> 4;
      if ( v58 > 9 )
        v57 = 87;
      *((_WORD *)v65 + (unsigned int)(3 * v53)) = v58 + v57;
      v59 = 48;
      v60 = v56 & 0xF;
      if ( v60 > 9 )
        v59 = 87;
      *((_WORD *)v65 + (unsigned int)(v3 + 28)) = v60 + v59;
      *((_WORD *)v65 + (unsigned int)(v3 + 29)) = 32;
    }
    HIWORD(v66) = 0;
  }
  else
  {
    LODWORD(v65[0]) = 48;
  }
  return AELogAutoEnrollmentEvent(4u, 0, 0, 0x80000040, 1, 0, 1u, (char)v65);
}

```

## disassembly

```asm
0x1800015d0  push    rbp
0x1800015d2  push    rbx
0x1800015d3  lea     rbp, [rsp-4Fh]
0x1800015d8  sub     rsp, 0F8h
0x1800015df  mov     rax, cs:__security_cookie
0x1800015e6  xor     rax, rsp
0x1800015e9  mov     [rbp+57h+var_20], rax
0x1800015ed  xorps   xmm1, xmm1
0x1800015f0  mov     [rbp+57h+pcbData], 14h
0x1800015f7  xor     ecx, ecx
0x1800015f9  lea     r9, [rbp+57h+pcbData]; pcbData
0x1800015fd  mov     rax, rdx
0x180001600  mov     [rbp+57h+var_A8], ecx
0x180001603  mov     [rbp+57h+var_30], rcx
0x180001607  lea     r8, [rbp+57h+pvData]; pvData
0x18000160b  xorps   xmm0, xmm0
0x18000160e  mov     rcx, rax; pCertContext
0x180001611  mov     edx, 3; dwPropId
0x180001616  movups  [rbp+57h+pvData], xmm0
0x18000161a  movups  [rbp+57h+var_A0], xmm1
0x18000161e  movups  [rbp+57h+var_90], xmm1
0x180001622  movups  [rbp+57h+var_80], xmm1
0x180001626  movups  [rbp+57h+var_70], xmm1
0x18000162a  movups  [rbp+57h+var_60], xmm1
0x18000162e  movups  [rbp+57h+var_50], xmm1
0x180001632  movups  [rbp+57h+var_40], xmm1
0x180001636  call    cs:__imp_CertGetCertificateContextProperty
0x18000163c  test    eax, eax
0x18000163e  jz      loc_180001A07
0x180001644  mov     [rsp+100h+arg_0], rsi
0x18000164c  xor     eax, eax
0x18000164e  mov     [rsp+100h+arg_10], rdi
0x180001656  mov     ebx, 30h ; '0'
0x18000165b  mov     [rsp+100h+var_10], r14
0x180001663  mov     edi, eax
0x180001665  mov     r14d, 20h ; ' '
0x18000166b  mov     esi, 57h ; 'W'
0x180001670  mov     ecx, edi
0x180001672  lea     r11d, [rdi+rdi*2]
0x180001676  mov     edx, ebx
0x180001678  movzx   r9d, byte ptr [rbp+rcx+57h+pvData]
0x18000167e  movzx   ecx, r9b
0x180001682  shr     cl, 4
0x180001685  movzx   r8d, cl
0x180001689  cmp     r8d, 9
0x18000168d  cmova   dx, si
0x180001691  and     r9b, 0Fh
0x180001695  add     dx, r8w
0x180001699  movzx   ecx, r9b
0x18000169d  cmp     ecx, 9
0x1800016a0  mov     word ptr [rbp+r11*2+57h+var_A0], dx
0x1800016a6  mov     r8d, ebx
0x1800016a9  cmova   r8w, si
0x1800016ae  add     r8w, cx
0x1800016b2  lea     ecx, [r11+1]
0x1800016b6  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x1800016bc  lea     ecx, [r11+2]
0x1800016c0  mov     word ptr [rbp+rcx*2+57h+var_A0], r14w
0x1800016c6  mov     r8d, ebx
0x1800016c9  lea     ecx, [rdi+1]
0x1800016cc  movzx   r9d, byte ptr [rbp+rcx+57h+pvData]
0x1800016d2  movzx   ecx, r9b
0x1800016d6  shr     cl, 4
0x1800016d9  movzx   edx, cl
0x1800016dc  lea     ecx, [r11+3]
0x1800016e0  cmp     edx, 9
0x1800016e3  cmova   r8w, si
0x1800016e8  and     r9b, 0Fh
0x1800016ec  add     r8w, dx
0x1800016f0  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x1800016f6  mov     r8d, ebx
0x1800016f9  movzx   ecx, r9b
0x1800016fd  lea     r9d, [rdi+2]
0x180001701  movzx   r10d, byte ptr [rbp+r9+57h+pvData]
0x180001707  cmp     ecx, 9
0x18000170a  cmova   r8w, si
0x18000170f  add     r8w, cx
0x180001713  lea     ecx, [r11+4]
0x180001717  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x18000171d  lea     ecx, [r11+5]
0x180001721  mov     word ptr [rbp+rcx*2+57h+var_A0], r14w
0x180001727  mov     r8d, ebx
0x18000172a  movzx   ecx, r10b
0x18000172e  shr     cl, 4
0x180001731  movzx   edx, cl
0x180001734  lea     ecx, [r9+r9*2]
0x180001738  cmp     edx, 9
0x18000173b  lea     r9d, [rdi+3]
0x18000173f  cmova   r8w, si
0x180001744  and     r10b, 0Fh
0x180001748  add     r8w, dx
0x18000174c  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x180001752  mov     r8d, ebx
0x180001755  movzx   ecx, r10b
0x180001759  movzx   r10d, byte ptr [rbp+r9+57h+pvData]
0x18000175f  cmp     ecx, 9
0x180001762  cmova   r8w, si
0x180001767  add     r8w, cx
0x18000176b  lea     ecx, [r11+7]
0x18000176f  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x180001775  lea     ecx, [r11+8]
0x180001779  mov     word ptr [rbp+rcx*2+57h+var_A0], r14w
0x18000177f  mov     r8d, ebx
0x180001782  movzx   ecx, r10b
0x180001786  shr     cl, 4
0x180001789  movzx   edx, cl
0x18000178c  lea     ecx, [r9+r9*2]
0x180001790  cmp     edx, 9
0x180001793  cmova   r8w, si
0x180001798  and     r10b, 0Fh
0x18000179c  add     r8w, dx
0x1800017a0  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x1800017a6  mov     r8d, ebx
0x1800017a9  movzx   ecx, r10b
0x1800017ad  cmp     ecx, 9
0x1800017b0  cmova   r8w, si
0x1800017b5  add     r8w, cx
0x1800017b9  lea     ecx, [r11+0Ah]
0x1800017bd  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x1800017c3  lea     r9d, [rdi+4]
0x1800017c7  movzx   r10d, byte ptr [rbp+r9+57h+pvData]
0x1800017cd  lea     ecx, [r11+0Bh]
0x1800017d1  mov     word ptr [rbp+rcx*2+57h+var_A0], r14w
0x1800017d7  mov     r8d, ebx
0x1800017da  movzx   ecx, r10b
0x1800017de  shr     cl, 4
0x1800017e1  movzx   edx, cl
0x1800017e4  lea     ecx, [r9+r9*2]
0x1800017e8  cmp     edx, 9
0x1800017eb  lea     r9d, [rdi+5]
0x1800017ef  cmova   r8w, si
0x1800017f4  and     r10b, 0Fh
0x1800017f8  add     r8w, dx
0x1800017fc  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x180001802  mov     r8d, ebx
0x180001805  movzx   ecx, r10b
0x180001809  movzx   r10d, byte ptr [rbp+r9+57h+pvData]
0x18000180f  cmp     ecx, 9
0x180001812  cmova   r8w, si
0x180001817  add     r8w, cx
0x18000181b  lea     ecx, [r11+0Dh]
0x18000181f  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x180001825  lea     ecx, [r11+0Eh]
0x180001829  mov     word ptr [rbp+rcx*2+57h+var_A0], r14w
0x18000182f  mov     r8d, ebx
0x180001832  movzx   ecx, r10b
0x180001836  shr     cl, 4
0x180001839  movzx   edx, cl
0x18000183c  lea     ecx, [r9+r9*2]
0x180001840  cmp     edx, 9
0x180001843  lea     r9d, [rdi+6]
0x180001847  cmova   r8w, si
0x18000184c  and     r10b, 0Fh
0x180001850  add     r8w, dx
0x180001854  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x18000185a  mov     r8d, ebx
0x18000185d  movzx   ecx, r10b
0x180001861  movzx   r10d, byte ptr [rbp+r9+57h+pvData]
0x180001867  cmp     ecx, 9
0x18000186a  cmova   r8w, si
0x18000186f  add     r8w, cx
0x180001873  lea     ecx, [r11+10h]
0x180001877  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x18000187d  lea     ecx, [r11+11h]
0x180001881  mov     word ptr [rbp+rcx*2+57h+var_A0], r14w
0x180001887  mov     r8d, ebx
0x18000188a  movzx   ecx, r10b
0x18000188e  shr     cl, 4
0x180001891  movzx   edx, cl
0x180001894  lea     ecx, [r9+r9*2]
0x180001898  cmp     edx, 9
0x18000189b  lea     r9d, [rdi+7]
0x18000189f  cmova   r8w, si
0x1800018a4  and     r10b, 0Fh
0x1800018a8  add     r8w, dx
0x1800018ac  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x1800018b2  mov     r8d, ebx
0x1800018b5  movzx   ecx, r10b
0x1800018b9  movzx   r10d, byte ptr [rbp+r9+57h+pvData]
0x1800018bf  cmp     ecx, 9
0x1800018c2  cmova   r8w, si
0x1800018c7  add     r8w, cx
0x1800018cb  lea     ecx, [r11+13h]
0x1800018cf  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x1800018d5  lea     ecx, [r11+14h]
0x1800018d9  mov     word ptr [rbp+rcx*2+57h+var_A0], r14w
0x1800018df  mov     r8d, ebx
0x1800018e2  movzx   ecx, r10b
0x1800018e6  shr     cl, 4
0x1800018e9  movzx   edx, cl
0x1800018ec  lea     ecx, [r9+r9*2]
0x1800018f0  cmp     edx, 9
0x1800018f3  cmova   r8w, si
0x1800018f8  and     r10b, 0Fh
0x1800018fc  add     r8w, dx
0x180001900  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x180001906  mov     r8d, ebx
0x180001909  movzx   ecx, r10b
0x18000190d  cmp     ecx, 9
0x180001910  cmova   r8w, si
0x180001915  lea     r9d, [rdi+8]
0x180001919  movzx   r10d, byte ptr [rbp+r9+57h+pvData]
0x18000191f  add     r8w, cx
0x180001923  lea     ecx, [r11+16h]
0x180001927  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x18000192d  lea     ecx, [r11+17h]
0x180001931  mov     word ptr [rbp+rcx*2+57h+var_A0], r14w
0x180001937  mov     r8d, ebx
0x18000193a  movzx   ecx, r10b
0x18000193e  shr     cl, 4
0x180001941  movzx   edx, cl
0x180001944  lea     ecx, [r9+r9*2]
0x180001948  cmp     edx, 9
0x18000194b  lea     r9d, [rdi+9]
0x18000194f  cmova   r8w, si
0x180001954  and     r10b, 0Fh
0x180001958  add     r8w, dx
0x18000195c  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x180001962  mov     r8d, ebx
0x180001965  movzx   ecx, r10b
0x180001969  movzx   r10d, byte ptr [rbp+r9+57h+pvData]
0x18000196f  cmp     ecx, 9
0x180001972  cmova   r8w, si
0x180001977  add     r8w, cx
0x18000197b  lea     ecx, [r11+19h]
0x18000197f  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x180001985  lea     ecx, [r11+1Ah]
0x180001989  mov     word ptr [rbp+rcx*2+57h+var_A0], r14w
0x18000198f  mov     r8d, ebx
0x180001992  movzx   ecx, r10b
0x180001996  shr     cl, 4
0x180001999  movzx   edx, cl
0x18000199c  lea     ecx, [r9+r9*2]
0x1800019a0  cmp     edx, 9
0x1800019a3  cmova   r8w, si
0x1800019a8  and     r10b, 0Fh
0x1800019ac  add     r8w, dx
0x1800019b0  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x1800019b6  mov     r8d, ebx
0x1800019b9  movzx   ecx, r10b
0x1800019bd  cmp     ecx, 9
0x1800019c0  cmova   r8w, si
0x1800019c5  add     edi, 0Ah
0x1800019c8  add     r8w, cx
0x1800019cc  lea     ecx, [r11+1Ch]
0x1800019d0  mov     word ptr [rbp+rcx*2+57h+var_A0], r8w
0x1800019d6  lea     ecx, [r11+1Dh]
0x1800019da  mov     word ptr [rbp+rcx*2+57h+var_A0], r14w
0x1800019e0  cmp     edi, 14h
0x1800019e3  jb      loc_180001670
0x1800019e9  mov     r14, [rsp+100h+var_10]
0x1800019f1  mov     rdi, [rsp+100h+arg_10]
0x1800019f9  mov     rsi, [rsp+100h+arg_0]
0x180001a01  mov     word ptr [rbp+57h+var_30+6], ax
0x180001a05  jmp     short loc_180001A10
0x180001a07  mov     dword ptr [rbp+57h+var_A0], 30h ; '0'
0x180001a0e  xor     eax, eax
0x180001a10  lea     rcx, [rbp+57h+var_A0]
0x180001a14  mov     r9d, 80000040h
0x180001a1a  mov     [rsp+100h+var_C8], rcx
0x180001a1f  xor     r8d, r8d
0x180001a22  mov     [rsp+100h+var_D0], 1
0x180001a2a  xor     edx, edx
0x180001a2c  mov     [rsp+100h+var_D8], rax
0x180001a31  mov     ecx, 4
0x180001a36  mov     [rsp+100h+var_E0], 1
0x180001a3e  call    AELogAutoEnrollmentEvent
0x180001a43  mov     rcx, [rbp+57h+var_20]
0x180001a47  xor     rcx, rsp; StackCookie
0x180001a4a  call    __security_check_cookie
0x180001a4f  add     rsp, 0F8h
0x180001a56  pop     rbx
0x180001a57  pop     rbp
0x180001a58  retn
```
