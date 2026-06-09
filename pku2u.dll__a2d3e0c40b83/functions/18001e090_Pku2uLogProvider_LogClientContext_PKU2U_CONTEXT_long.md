# Pku2uLogProvider::LogClientContext(_PKU2U_CONTEXT *,long)

- ea: `0x18001e090`
- end: `0x18001e361`
- name: `?LogClientContext@Pku2uLogProvider@@SAXPEAU_PKU2U_CONTEXT@@J@Z`
- size: `721`
- prototype: `void __fastcall(struct _PKU2U_CONTEXT *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001cc90`

## callees

- `0x180014c60`
- `0x180014d60`
- `0x180017af0`
- `0x18001e090`
- `0x1800210f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e337`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e337`

## pseudocode

```c
void __fastcall Pku2uLogProvider::LogClientContext(struct _PKU2U_CONTEXT *a1, unsigned __int64 a2)
{
  int v2; // edi
  TraceLoggingCorrelationVector *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  char v8; // al
  __int64 v9; // rax
  char v10; // [rsp+30h] [rbp-D0h] BYREF
  char v11; // [rsp+31h] [rbp-CFh] BYREF
  char v12; // [rsp+32h] [rbp-CEh] BYREF
  int v13; // [rsp+34h] [rbp-CCh] BYREF
  _DWORD v14[2]; // [rsp+38h] [rbp-C8h] BYREF
  struct _PKU2U_CONTEXT *v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v17; // [rsp+50h] [rbp-B0h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v19; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-80h] BYREF
  char *v21; // [rsp+90h] [rbp-70h]
  int v22; // [rsp+98h] [rbp-68h]
  int v23; // [rsp+9Ch] [rbp-64h]
  __int64 *v24; // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+A8h] [rbp-58h]
  __int128 *v26; // [rsp+B0h] [rbp-50h]
  __int64 v27; // [rsp+B8h] [rbp-48h]
  _DWORD *v28; // [rsp+C0h] [rbp-40h]
  __int64 v29; // [rsp+C8h] [rbp-38h]
  __int64 v30; // [rsp+D0h] [rbp-30h]
  _DWORD v31[2]; // [rsp+D8h] [rbp-28h] BYREF
  char *v32; // [rsp+E0h] [rbp-20h]
  __int64 v33; // [rsp+E8h] [rbp-18h]
  char *v34; // [rsp+F0h] [rbp-10h]
  __int64 v35; // [rsp+F8h] [rbp-8h]
  int *v36; // [rsp+100h] [rbp+0h]
  __int64 v37; // [rsp+108h] [rbp+8h]
  char *v38; // [rsp+110h] [rbp+10h]
  __int64 v39; // [rsp+118h] [rbp+18h]
  _DWORD *v40; // [rsp+120h] [rbp+20h]
  __int64 v41; // [rsp+128h] [rbp+28h]
  struct _PKU2U_CONTEXT **v42; // [rsp+130h] [rbp+30h]
  __int64 v43; // [rsp+138h] [rbp+38h]
  char *v44; // [rsp+140h] [rbp+40h]
  int v45; // [rsp+148h] [rbp+48h]
  int v46; // [rsp+14Ch] [rbp+4Ch]
  char v47[16]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v48; // [rsp+160h] [rbp+60h]
  __int128 v49; // [rsp+170h] [rbp+70h]
  __int128 v50; // [rsp+180h] [rbp+80h]
  __int128 v51; // [rsp+190h] [rbp+90h]
  __int128 v52; // [rsp+1A0h] [rbp+A0h]
  __int128 v53; // [rsp+1B0h] [rbp+B0h]
  __int128 v54; // [rsp+1C0h] [rbp+C0h]
  char v55; // [rsp+1D0h] [rbp+D0h]

  v2 = a2;
  if ( Pku2uLogProvider::m_initialized && Pku2uLogProvider::IsEnabled((unsigned __int8)a1, a2) )
  {
    *(_OWORD *)v47 = 0;
    v55 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    if ( !TraceLoggingCorrelationVector::ToString(v4, v47) )
      v47[0] = 0;
    v19 = 0;
    v17 = 0;
    if ( a1 )
    {
      v5 = *((_QWORD *)a1 + 4);
      if ( v5 )
      {
        v19 = *(_OWORD *)(v5 + 120);
        v17 = *(_OWORD *)(v5 + 88);
      }
    }
    v6 = *((_QWORD *)Pku2uLogProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v15 = a1;
      v14[0] = v2;
      if ( a1 )
      {
        v10 = *((_BYTE *)a1 + 172);
        v13 = *((_DWORD *)a1 + 16);
        v11 = *((_BYTE *)a1 + 68);
        v7 = *((_QWORD *)a1 + 2);
        if ( v7 )
        {
          v8 = *(_BYTE *)(v7 + 32);
          goto LABEL_16;
        }
      }
      else
      {
        v10 = 0;
        v13 = 0;
        v11 = 0;
      }
      v8 = -1;
LABEL_16:
      v12 = v8;
      v9 = -1;
      v16 = 0x1000000;
      do
        ++v9;
      while ( v47[v9] );
      EventDescriptor.Keyword = 0x400000000000LL;
      v45 = v9 + 1;
      v44 = v47;
      v42 = &v15;
      v46 = 0;
      v40 = v14;
      v43 = 8;
      v38 = &v10;
      v36 = &v13;
      v34 = &v11;
      v32 = &v12;
      v28 = v31;
      v30 = *((_QWORD *)&v17 + 1);
      v31[0] = (unsigned __int16)v17;
      v26 = &v19;
      v24 = &v16;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = *(_QWORD *)(v6 + 8);
      v41 = 4;
      v39 = 1;
      v37 = 4;
      v35 = 1;
      v33 = 1;
      v29 = 2;
      v31[1] = 0;
      v27 = 16;
      v25 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      v21 = byte_18004CA21;
      UserData.Reserved = 2;
      v22 = 145;
      v23 = 1;
      v14[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v6 + 32), &EventDescriptor, 0, 0, 0xDu, &UserData);
    }
  }
}

```

## disassembly

```asm
0x18001e090  mov     [rsp-8+arg_0], rbx
0x18001e095  mov     [rsp-8+arg_8], rdi
0x18001e09a  push    rbp
0x18001e09b  lea     rbp, [rsp-0F0h]
0x18001e0a3  sub     rsp, 1F0h
0x18001e0aa  mov     rax, cs:__security_cookie
0x18001e0b1  xor     rax, rsp
0x18001e0b4  mov     [rbp+0F0h+var_10], rax
0x18001e0bb  cmp     cs:?m_initialized@Pku2uLogProvider@@0_NA, 0; bool Pku2uLogProvider::m_initialized
0x18001e0c2  mov     edi, edx
0x18001e0c4  mov     rbx, rcx
0x18001e0c7  jz      loc_18001E33D
0x18001e0cd  call    ?IsEnabled@Pku2uLogProvider@@SA_NE_K@Z; Pku2uLogProvider::IsEnabled(uchar,unsigned __int64)
0x18001e0d2  test    al, al
0x18001e0d4  jz      loc_18001E33D
0x18001e0da  xorps   xmm0, xmm0
0x18001e0dd  lea     rdx, [rbp+0F0h+var_A0]; char *
0x18001e0e1  xor     eax, eax
0x18001e0e3  movups  xmmword ptr [rbp+0F0h+var_A0], xmm0
0x18001e0e7  mov     [rbp+0F0h+var_20], al
0x18001e0ed  movups  [rbp+0F0h+var_90], xmm0
0x18001e0f1  movups  [rbp+0F0h+var_80], xmm0
0x18001e0f5  movups  [rbp+0F0h+var_70], xmm0
0x18001e0fc  movups  [rbp+0F0h+var_60], xmm0
0x18001e103  movups  [rbp+0F0h+var_50], xmm0
0x18001e10a  movups  [rbp+0F0h+var_40], xmm0
0x18001e111  movups  [rbp+0F0h+var_30], xmm0
0x18001e118  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x18001e11d  test    al, al
0x18001e11f  jnz     short loc_18001E124
0x18001e121  mov     [rbp+0F0h+var_A0], al
0x18001e124  xorps   xmm0, xmm0
0x18001e127  xorps   xmm1, xmm1
0x18001e12a  movups  [rsp+1F0h+var_180], xmm0
0x18001e12f  movups  [rsp+1F0h+var_1A0], xmm1
0x18001e134  test    rbx, rbx
0x18001e137  jz      short loc_18001E154
0x18001e139  mov     rax, [rbx+20h]
0x18001e13d  test    rax, rax
0x18001e140  jz      short loc_18001E154
0x18001e142  movups  xmm0, xmmword ptr [rax+78h]
0x18001e146  movups  [rsp+1F0h+var_180], xmm0
0x18001e14b  movups  xmm1, xmmword ptr [rax+58h]
0x18001e14f  movups  [rsp+1F0h+var_1A0], xmm1
0x18001e154  call    ?Instance@Pku2uLogProvider@@KAPEAV1@XZ; Pku2uLogProvider::Instance(void)
0x18001e159  mov     rcx, [rax+8]
0x18001e15d  mov     eax, [rcx]
0x18001e15f  cmp     eax, 5
0x18001e162  jbe     loc_18001E33D
0x18001e168  mov     rdx, [rcx+18h]
0x18001e16c  mov     r9, 400000000000h
0x18001e176  mov     rax, [rcx+10h]
0x18001e17a  test    r9, rax
0x18001e17d  jz      loc_18001E33D
0x18001e183  mov     rax, rdx
0x18001e186  and     rax, r9
0x18001e189  cmp     rax, rdx
0x18001e18c  jnz     loc_18001E33D
0x18001e192  xor     r8d, r8d; ActivityId
0x18001e195  mov     [rsp+1F0h+var_1B0], rbx
0x18001e19a  mov     [rsp+1F0h+var_1B8], edi
0x18001e19e  test    rbx, rbx
0x18001e1a1  jz      short loc_18001E1CC
0x18001e1a3  movzx   eax, byte ptr [rbx+0ACh]
0x18001e1aa  mov     [rsp+1F0h+var_1C0], al
0x18001e1ae  mov     eax, [rbx+40h]
0x18001e1b1  mov     [rsp+1F0h+var_1BC], eax
0x18001e1b5  movzx   eax, byte ptr [rbx+44h]
0x18001e1b9  mov     [rsp+1F0h+var_1BF], al
0x18001e1bd  mov     rax, [rbx+10h]
0x18001e1c1  test    rax, rax
0x18001e1c4  jz      short loc_18001E1DB
0x18001e1c6  movzx   eax, byte ptr [rax+20h]
0x18001e1ca  jmp     short loc_18001E1DD
0x18001e1cc  mov     [rsp+1F0h+var_1C0], r8b
0x18001e1d1  mov     [rsp+1F0h+var_1BC], r8d
0x18001e1d6  mov     [rsp+1F0h+var_1BF], r8b
0x18001e1db  mov     al, 0FFh
0x18001e1dd  mov     [rsp+1F0h+var_1BE], al
0x18001e1e1  lea     rdx, [rbp+0F0h+var_A0]
0x18001e1e5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001e1ec  mov     [rsp+1F0h+var_1A8], 1000000h
0x18001e1f5  inc     rax
0x18001e1f8  cmp     [rdx+rax], r8b
0x18001e1fc  jnz     short loc_18001E1F5
0x18001e1fe  inc     eax
0x18001e200  mov     [rsp+1F0h+EventDescriptor.Keyword], r9
0x18001e205  mov     [rbp+0F0h+var_A8], eax
0x18001e208  lea     rdx, [rbp+0F0h+var_A0]
0x18001e20c  mov     [rbp+0F0h+var_B0], rdx
0x18001e210  lea     rax, [rsp+1F0h+var_1B0]
0x18001e215  mov     [rbp+0F0h+var_C0], rax
0x18001e219  lea     rdx, _TraceLoggingMetadata
0x18001e220  lea     rax, [rsp+1F0h+var_1B8]
0x18001e225  mov     [rbp+0F0h+var_A4], r8d
0x18001e229  mov     [rbp+0F0h+var_D0], rax
0x18001e22d  xor     r9d, r9d; RelatedActivityId
0x18001e230  lea     rax, [rsp+1F0h+var_1C0]
0x18001e235  mov     [rbp+0F0h+var_B8], 8
0x18001e23d  mov     [rbp+0F0h+var_E0], rax
0x18001e241  lea     rax, [rsp+1F0h+var_1BC]
0x18001e246  mov     [rbp+0F0h+var_F0], rax
0x18001e24a  lea     rax, [rsp+1F0h+var_1BF]
0x18001e24f  mov     [rbp+0F0h+var_100], rax
0x18001e253  lea     rax, [rsp+1F0h+var_1BE]
0x18001e258  mov     [rbp+0F0h+var_110], rax
0x18001e25c  lea     rax, [rbp+0F0h+var_118]
0x18001e260  mov     [rbp+0F0h+var_130], rax
0x18001e264  mov     rax, qword ptr [rsp+1F0h+var_1A0+8]
0x18001e269  mov     [rbp+0F0h+var_120], rax
0x18001e26d  movzx   eax, word ptr [rsp+1F0h+var_1A0]
0x18001e272  mov     [rbp+0F0h+var_118], eax
0x18001e275  lea     rax, [rsp+1F0h+var_180]
0x18001e27a  mov     [rbp+0F0h+var_140], rax
0x18001e27e  lea     rax, [rsp+1F0h+var_1A8]
0x18001e283  mov     [rbp+0F0h+var_150], rax
0x18001e287  movzx   eax, cs:word_18004CA17
0x18001e28e  mov     dword ptr [rsp+1F0h+EventDescriptor.Level], eax
0x18001e292  mov     rax, [rcx+8]
0x18001e296  mov     [rbp+0F0h+var_170.Ptr], rax
0x18001e29a  mov     [rbp+0F0h+var_C8], 4
0x18001e2a2  mov     [rbp+0F0h+var_D8], 1
0x18001e2aa  mov     [rbp+0F0h+var_E8], 4
0x18001e2b2  mov     [rbp+0F0h+var_F8], 1
0x18001e2ba  mov     [rbp+0F0h+var_108], 1
0x18001e2c2  mov     [rbp+0F0h+var_128], 2
0x18001e2ca  mov     [rbp+0F0h+var_114], r8d
0x18001e2ce  mov     [rbp+0F0h+var_138], 10h
0x18001e2d6  mov     [rbp+0F0h+var_148], 8
0x18001e2de  mov     dword ptr [rsp+1F0h+EventDescriptor.Id], 0B000000h
0x18001e2e6  movzx   eax, word ptr [rax]
0x18001e2e9  mov     [rbp+0F0h+var_170.Size], eax
0x18001e2ec  lea     rax, byte_18004CA21
0x18001e2f3  mov     [rbp+0F0h+var_160], rax
0x18001e2f7  lea     rax, _TraceLoggingMetadataEnd
0x18001e2fe  sub     eax, edx
0x18001e300  mov     dword ptr [rbp+0F0h+var_170.0Ch], 2
0x18001e307  mov     [rbp+0F0h+var_158], 91h
0x18001e30e  lea     rdx, [rsp+1F0h+EventDescriptor]; EventDescriptor
0x18001e313  mov     [rbp+0F0h+var_154], 1
0x18001e31a  mov     [rsp+1F0h+var_1B4], eax
0x18001e31e  mov     eax, [rsp+1F0h+var_1B4]
0x18001e322  mov     rcx, [rcx+20h]; RegHandle
0x18001e326  lea     rax, [rbp+0F0h+var_170]
0x18001e32a  mov     [rsp+1F0h+UserData], rax; UserData
0x18001e32f  mov     [rsp+1F0h+UserDataCount], 0Dh; UserDataCount
0x18001e337  call    cs:__imp_EventWriteTransfer
0x18001e33d  mov     rcx, [rbp+0F0h+var_10]
0x18001e344  xor     rcx, rsp; StackCookie
0x18001e347  call    __security_check_cookie
0x18001e34c  lea     r11, [rsp+1F0h+var_s0]
0x18001e354  mov     rbx, [r11+10h]
0x18001e358  mov     rdi, [r11+18h]
0x18001e35c  mov     rsp, r11
0x18001e35f  pop     rbp
0x18001e360  retn
```
