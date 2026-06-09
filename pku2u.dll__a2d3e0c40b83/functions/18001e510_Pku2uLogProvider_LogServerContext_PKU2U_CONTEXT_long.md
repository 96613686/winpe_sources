# Pku2uLogProvider::LogServerContext(_PKU2U_CONTEXT *,long)

- ea: `0x18001e510`
- end: `0x18001e85d`
- name: `?LogServerContext@Pku2uLogProvider@@SAXPEAU_PKU2U_CONTEXT@@J@Z`
- size: `845`
- prototype: `void __fastcall(struct _PKU2U_CONTEXT *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001b990`

## callees

- `0x180014c60`
- `0x180014d60`
- `0x180017af0`
- `0x18001e510`
- `0x1800210f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e833`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e833`

## pseudocode

```c
void __fastcall Pku2uLogProvider::LogServerContext(struct _PKU2U_CONTEXT *a1, unsigned __int64 a2)
{
  int v2; // edi
  TraceLoggingCorrelationVector *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // r10
  unsigned __int16 *v7; // rdx
  unsigned __int16 *v8; // r8
  __int64 v9; // rax
  char v10; // al
  __int64 v11; // rax
  int v12; // ecx
  int v13; // ecx
  char v14; // [rsp+30h] [rbp-D0h] BYREF
  char v15; // [rsp+31h] [rbp-CFh] BYREF
  char v16; // [rsp+32h] [rbp-CEh] BYREF
  int v17; // [rsp+34h] [rbp-CCh] BYREF
  _DWORD v18[2]; // [rsp+38h] [rbp-C8h] BYREF
  struct _PKU2U_CONTEXT *v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v23; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-80h] BYREF
  char *v25; // [rsp+90h] [rbp-70h]
  int v26; // [rsp+98h] [rbp-68h]
  int v27; // [rsp+9Ch] [rbp-64h]
  __int64 *v28; // [rsp+A0h] [rbp-60h]
  __int64 v29; // [rsp+A8h] [rbp-58h]
  __int128 *v30; // [rsp+B0h] [rbp-50h]
  __int64 v31; // [rsp+B8h] [rbp-48h]
  _DWORD *v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+C8h] [rbp-38h]
  __int64 v34; // [rsp+D0h] [rbp-30h]
  _DWORD v35[2]; // [rsp+D8h] [rbp-28h] BYREF
  char *v36; // [rsp+E0h] [rbp-20h]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  _DWORD *v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+F8h] [rbp-8h]
  __int64 v40; // [rsp+100h] [rbp+0h]
  _DWORD v41[2]; // [rsp+108h] [rbp+8h] BYREF
  _DWORD *v42; // [rsp+110h] [rbp+10h]
  __int64 v43; // [rsp+118h] [rbp+18h]
  __int64 v44; // [rsp+120h] [rbp+20h]
  _DWORD v45[2]; // [rsp+128h] [rbp+28h] BYREF
  char *v46; // [rsp+130h] [rbp+30h]
  __int64 v47; // [rsp+138h] [rbp+38h]
  int *v48; // [rsp+140h] [rbp+40h]
  __int64 v49; // [rsp+148h] [rbp+48h]
  char *v50; // [rsp+150h] [rbp+50h]
  __int64 v51; // [rsp+158h] [rbp+58h]
  _DWORD *v52; // [rsp+160h] [rbp+60h]
  __int64 v53; // [rsp+168h] [rbp+68h]
  struct _PKU2U_CONTEXT **v54; // [rsp+170h] [rbp+70h]
  __int64 v55; // [rsp+178h] [rbp+78h]
  char *v56; // [rsp+180h] [rbp+80h]
  int v57; // [rsp+188h] [rbp+88h]
  int v58; // [rsp+18Ch] [rbp+8Ch]
  char v59[16]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v60; // [rsp+1A0h] [rbp+A0h]
  __int128 v61; // [rsp+1B0h] [rbp+B0h]
  __int128 v62; // [rsp+1C0h] [rbp+C0h]
  __int128 v63; // [rsp+1D0h] [rbp+D0h]
  __int128 v64; // [rsp+1E0h] [rbp+E0h]
  __int128 v65; // [rsp+1F0h] [rbp+F0h]
  __int128 v66; // [rsp+200h] [rbp+100h]
  char v67; // [rsp+210h] [rbp+110h]

  v2 = a2;
  if ( Pku2uLogProvider::m_initialized && Pku2uLogProvider::IsEnabled((unsigned __int8)a1, a2) )
  {
    *(_OWORD *)v59 = 0;
    v67 = 0;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    if ( !TraceLoggingCorrelationVector::ToString(v4, v59) )
      v59[0] = 0;
    v23 = 0;
    v21 = 0;
    if ( a1 )
    {
      v5 = *((_QWORD *)a1 + 4);
      if ( v5 )
      {
        v23 = *(_OWORD *)(v5 + 120);
        v21 = *(_OWORD *)(v5 + 88);
      }
    }
    v6 = *((_QWORD *)Pku2uLogProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v19 = a1;
      v18[0] = v2;
      if ( a1 )
      {
        v7 = (unsigned __int16 *)((char *)a1 + 328);
        v14 = *((_BYTE *)a1 + 172);
        v8 = (unsigned __int16 *)((char *)a1 + 184);
        v17 = *((_DWORD *)a1 + 16);
        v15 = *((_BYTE *)a1 + 68);
        v9 = *((_QWORD *)a1 + 2);
        if ( v9 )
        {
          v10 = *(_BYTE *)(v9 + 32);
          goto LABEL_16;
        }
      }
      else
      {
        v14 = 0;
        v7 = 0;
        v17 = 0;
        v8 = 0;
        v15 = 0;
      }
      v10 = -1;
LABEL_16:
      v16 = v10;
      v11 = -1;
      v20 = 0x1000000;
      do
        ++v11;
      while ( v59[v11] );
      v58 = 0;
      v57 = v11 + 1;
      v56 = v59;
      v54 = &v19;
      v52 = v18;
      v50 = &v14;
      v48 = &v17;
      v46 = &v15;
      v42 = v45;
      v55 = 8;
      v53 = 4;
      v51 = 1;
      v49 = 4;
      v47 = 1;
      v43 = 2;
      v12 = *v7;
      v44 = *((_QWORD *)v7 + 1);
      v38 = v41;
      v45[0] = v12;
      v45[1] = 0;
      v39 = 2;
      v13 = *v8;
      v40 = *((_QWORD *)v8 + 1);
      v36 = &v16;
      v32 = v35;
      v34 = *((_QWORD *)&v21 + 1);
      v35[0] = (unsigned __int16)v21;
      v30 = &v23;
      v28 = &v20;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = *(_QWORD *)(v6 + 8);
      v41[0] = v13;
      v41[1] = 0;
      v37 = 1;
      v33 = 2;
      v35[1] = 0;
      v31 = 16;
      v29 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x400000000000LL;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v25 = &byte_18004C8EF;
      UserData.Reserved = 2;
      v26 = 174;
      v27 = 1;
      v18[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v6 + 32), &EventDescriptor, 0, 0, 0x11u, &UserData);
    }
  }
}

```

## disassembly

```asm
0x18001e510  mov     [rsp-8+arg_0], rbx
0x18001e515  mov     [rsp-8+arg_8], rdi
0x18001e51a  push    rbp
0x18001e51b  lea     rbp, [rsp-130h]
0x18001e523  sub     rsp, 230h
0x18001e52a  mov     rax, cs:__security_cookie
0x18001e531  xor     rax, rsp
0x18001e534  mov     [rbp+130h+var_10], rax
0x18001e53b  cmp     cs:?m_initialized@Pku2uLogProvider@@0_NA, 0; bool Pku2uLogProvider::m_initialized
0x18001e542  mov     edi, edx
0x18001e544  mov     rbx, rcx
0x18001e547  jz      loc_18001E839
0x18001e54d  call    ?IsEnabled@Pku2uLogProvider@@SA_NE_K@Z; Pku2uLogProvider::IsEnabled(uchar,unsigned __int64)
0x18001e552  test    al, al
0x18001e554  jz      loc_18001E839
0x18001e55a  xorps   xmm0, xmm0
0x18001e55d  lea     rdx, [rbp+130h+var_A0]; char *
0x18001e564  xor     eax, eax
0x18001e566  movups  xmmword ptr [rbp+130h+var_A0], xmm0
0x18001e56d  mov     [rbp+130h+var_20], al
0x18001e573  movups  [rbp+130h+var_90], xmm0
0x18001e57a  movups  [rbp+130h+var_80], xmm0
0x18001e581  movups  [rbp+130h+var_70], xmm0
0x18001e588  movups  [rbp+130h+var_60], xmm0
0x18001e58f  movups  [rbp+130h+var_50], xmm0
0x18001e596  movups  [rbp+130h+var_40], xmm0
0x18001e59d  movups  [rbp+130h+var_30], xmm0
0x18001e5a4  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x18001e5a9  test    al, al
0x18001e5ab  jnz     short loc_18001E5B3
0x18001e5ad  mov     [rbp+130h+var_A0], al
0x18001e5b3  xorps   xmm0, xmm0
0x18001e5b6  xorps   xmm1, xmm1
0x18001e5b9  movups  [rsp+230h+var_1C0], xmm0
0x18001e5be  movups  [rsp+230h+var_1E0], xmm1
0x18001e5c3  test    rbx, rbx
0x18001e5c6  jz      short loc_18001E5E3
0x18001e5c8  mov     rax, [rbx+20h]
0x18001e5cc  test    rax, rax
0x18001e5cf  jz      short loc_18001E5E3
0x18001e5d1  movups  xmm0, xmmword ptr [rax+78h]
0x18001e5d5  movups  [rsp+230h+var_1C0], xmm0
0x18001e5da  movups  xmm1, xmmword ptr [rax+58h]
0x18001e5de  movups  [rsp+230h+var_1E0], xmm1
0x18001e5e3  call    ?Instance@Pku2uLogProvider@@KAPEAV1@XZ; Pku2uLogProvider::Instance(void)
0x18001e5e8  mov     r10, [rax+8]
0x18001e5ec  mov     eax, [r10]
0x18001e5ef  cmp     eax, 5
0x18001e5f2  jbe     loc_18001E839
0x18001e5f8  mov     rcx, [r10+18h]
0x18001e5fc  mov     r11, 400000000000h
0x18001e606  mov     rax, [r10+10h]
0x18001e60a  test    r11, rax
0x18001e60d  jz      loc_18001E839
0x18001e613  mov     rax, rcx
0x18001e616  and     rax, r11
0x18001e619  cmp     rax, rcx
0x18001e61c  jnz     loc_18001E839
0x18001e622  xor     r9d, r9d; RelatedActivityId
0x18001e625  mov     [rsp+230h+var_1F0], rbx
0x18001e62a  mov     [rsp+230h+var_1F8], edi
0x18001e62e  test    rbx, rbx
0x18001e631  jz      short loc_18001E66A
0x18001e633  movzx   eax, byte ptr [rbx+0ACh]
0x18001e63a  lea     rdx, [rbx+148h]
0x18001e641  mov     [rsp+230h+var_200], al
0x18001e645  lea     r8, [rbx+0B8h]
0x18001e64c  mov     eax, [rbx+40h]
0x18001e64f  mov     [rsp+230h+var_1FC], eax
0x18001e653  movzx   eax, byte ptr [rbx+44h]
0x18001e657  mov     [rsp+230h+var_1FF], al
0x18001e65b  mov     rax, [rbx+10h]
0x18001e65f  test    rax, rax
0x18001e662  jz      short loc_18001E67F
0x18001e664  movzx   eax, byte ptr [rax+20h]
0x18001e668  jmp     short loc_18001E681
0x18001e66a  mov     [rsp+230h+var_200], r9b
0x18001e66f  mov     rdx, r9
0x18001e672  mov     [rsp+230h+var_1FC], r9d
0x18001e677  mov     r8, r9
0x18001e67a  mov     [rsp+230h+var_1FF], r9b
0x18001e67f  mov     al, 0FFh
0x18001e681  mov     [rsp+230h+var_1FE], al
0x18001e685  lea     rcx, [rbp+130h+var_A0]
0x18001e68c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001e693  mov     [rsp+230h+var_1E8], 1000000h
0x18001e69c  nop     dword ptr [rax+00h]
0x18001e6a0  inc     rax
0x18001e6a3  cmp     [rcx+rax], r9b
0x18001e6a7  jnz     short loc_18001E6A0
0x18001e6a9  inc     eax
0x18001e6ab  mov     [rbp+130h+var_A4], r9d
0x18001e6b2  mov     [rbp+130h+var_A8], eax
0x18001e6b8  lea     rcx, [rbp+130h+var_A0]
0x18001e6bf  mov     [rbp+130h+var_B0], rcx
0x18001e6c6  lea     rax, [rsp+230h+var_1F0]
0x18001e6cb  mov     [rbp+130h+var_C0], rax
0x18001e6cf  lea     rax, [rsp+230h+var_1F8]
0x18001e6d4  mov     [rbp+130h+var_D0], rax
0x18001e6d8  lea     rax, [rsp+230h+var_200]
0x18001e6dd  mov     [rbp+130h+var_E0], rax
0x18001e6e1  lea     rax, [rsp+230h+var_1FC]
0x18001e6e6  mov     [rbp+130h+var_F0], rax
0x18001e6ea  lea     rax, [rsp+230h+var_1FF]
0x18001e6ef  mov     [rbp+130h+var_100], rax
0x18001e6f3  lea     rax, [rbp+130h+var_108]
0x18001e6f7  mov     [rbp+130h+var_120], rax
0x18001e6fb  mov     [rbp+130h+var_B8], 8
0x18001e703  mov     [rbp+130h+var_C8], 4
0x18001e70b  mov     [rbp+130h+var_D8], 1
0x18001e713  mov     [rbp+130h+var_E8], 4
0x18001e71b  mov     [rbp+130h+var_F8], 1
0x18001e723  mov     [rbp+130h+var_118], 2
0x18001e72b  movzx   ecx, word ptr [rdx]
0x18001e72e  mov     rax, [rdx+8]
0x18001e732  lea     rdx, [rsp+230h+EventDescriptor]; EventDescriptor
0x18001e737  mov     [rbp+130h+var_110], rax
0x18001e73b  lea     rax, [rbp+130h+var_128]
0x18001e73f  mov     [rbp+130h+var_140], rax
0x18001e743  mov     [rbp+130h+var_108], ecx
0x18001e746  mov     [rbp+130h+var_104], r9d
0x18001e74a  mov     [rbp+130h+var_138], 2
0x18001e752  mov     rax, [r8+8]
0x18001e756  movzx   ecx, word ptr [r8]
0x18001e75a  xor     r8d, r8d; ActivityId
0x18001e75d  mov     [rbp+130h+var_130], rax
0x18001e761  lea     rax, [rsp+230h+var_1FE]
0x18001e766  mov     [rbp+130h+var_150], rax
0x18001e76a  lea     rax, [rbp+130h+var_158]
0x18001e76e  mov     [rbp+130h+var_170], rax
0x18001e772  mov     rax, qword ptr [rsp+230h+var_1E0+8]
0x18001e777  mov     [rbp+130h+var_160], rax
0x18001e77b  movzx   eax, word ptr [rsp+230h+var_1E0]
0x18001e780  mov     [rbp+130h+var_158], eax
0x18001e783  lea     rax, [rsp+230h+var_1C0]
0x18001e788  mov     [rbp+130h+var_180], rax
0x18001e78c  lea     rax, [rsp+230h+var_1E8]
0x18001e791  mov     [rbp+130h+var_190], rax
0x18001e795  movzx   eax, cs:word_18004C8E5
0x18001e79c  mov     dword ptr [rsp+230h+EventDescriptor.Level], eax
0x18001e7a0  mov     rax, [r10+8]
0x18001e7a4  mov     [rbp+130h+var_1B0.Ptr], rax
0x18001e7a8  mov     [rbp+130h+var_128], ecx
0x18001e7ab  lea     rcx, _TraceLoggingMetadata
0x18001e7b2  mov     [rbp+130h+var_124], r9d
0x18001e7b6  mov     [rbp+130h+var_148], 1
0x18001e7be  mov     [rbp+130h+var_168], 2
0x18001e7c6  mov     [rbp+130h+var_154], r9d
0x18001e7ca  mov     [rbp+130h+var_178], 10h
0x18001e7d2  mov     [rbp+130h+var_188], 8
0x18001e7da  mov     dword ptr [rsp+230h+EventDescriptor.Id], 0B000000h
0x18001e7e2  mov     [rsp+230h+EventDescriptor.Keyword], r11
0x18001e7e7  movzx   eax, word ptr [rax]
0x18001e7ea  mov     [rbp+130h+var_1B0.Size], eax
0x18001e7ed  lea     rax, byte_18004C8EF
0x18001e7f4  mov     [rbp+130h+var_1A0], rax
0x18001e7f8  lea     rax, _TraceLoggingMetadataEnd
0x18001e7ff  sub     eax, ecx
0x18001e801  mov     dword ptr [rbp+130h+var_1B0.0Ch], 2
0x18001e808  mov     [rbp+130h+var_198], 0AEh
0x18001e80f  mov     [rbp+130h+var_194], 1
0x18001e816  mov     [rsp+230h+var_1F4], eax
0x18001e81a  mov     eax, [rsp+230h+var_1F4]
0x18001e81e  mov     rcx, [r10+20h]; RegHandle
0x18001e822  lea     rax, [rbp+130h+var_1B0]
0x18001e826  mov     [rsp+230h+UserData], rax; UserData
0x18001e82b  mov     [rsp+230h+UserDataCount], 11h; UserDataCount
0x18001e833  call    cs:__imp_EventWriteTransfer
0x18001e839  mov     rcx, [rbp+130h+var_10]
0x18001e840  xor     rcx, rsp; StackCookie
0x18001e843  call    __security_check_cookie
0x18001e848  lea     r11, [rsp+230h+var_s0]
0x18001e850  mov     rbx, [r11+10h]
0x18001e854  mov     rdi, [r11+18h]
0x18001e858  mov     rsp, r11
0x18001e85b  pop     rbp
0x18001e85c  retn
```
