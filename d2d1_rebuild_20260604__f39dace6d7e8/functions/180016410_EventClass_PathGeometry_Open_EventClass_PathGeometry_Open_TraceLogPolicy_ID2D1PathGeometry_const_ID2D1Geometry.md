# EventClass_PathGeometry_Open::EventClass_PathGeometry_Open(TraceLogPolicy *,ID2D1PathGeometry const *,ID2D1GeometrySink * *)

- ea: `0x180016410`
- end: `0x180016658`
- name: `??0EventClass_PathGeometry_Open@@QEAA@PEAVTraceLogPolicy@@PEBUID2D1PathGeometry@@PEAPEAUID2D1GeometrySink@@@Z`
- size: `584`
- prototype: `EventClass_PathGeometry_Open *__fastcall(EventClass_PathGeometry_Open *__hidden this, struct TraceLogPolicy *, const struct ID2D1PathGeometry *, struct ID2D1GeometrySink **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800160c0`
- `0x180165450`

## callees

- `0x180016410`
- `0x1801cd034`
- `0x18025b100`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180016630`
- `ntdll!EtwEventWriteTransfer` at `0x180016630`

## string_xrefs

- `0x180016578`: `IPathGeometry`

## pseudocode

```c
EventClass_PathGeometry_Open *__fastcall EventClass_PathGeometry_Open::EventClass_PathGeometry_Open(
        EventClass_PathGeometry_Open *this,
        struct TraceLogPolicy *a2,
        const struct ID2D1PathGeometry *a3,
        struct ID2D1GeometrySink **a4)
{
  unsigned int v6; // eax
  __int64 *v7; // rax
  __int64 v8; // rcx
  __int64 v10; // [rsp+30h] [rbp-D0h] BYREF
  const struct ID2D1PathGeometry *v11; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v15[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h]
  void *v17; // [rsp+70h] [rbp-90h] BYREF
  int v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+7Ch] [rbp-84h]
  void *v20; // [rsp+80h] [rbp-80h]
  int v21; // [rsp+88h] [rbp-78h]
  int v22; // [rsp+8Ch] [rbp-74h]
  const char *v23; // [rsp+90h] [rbp-70h]
  __int64 v24; // [rsp+98h] [rbp-68h]
  const char *v25; // [rsp+A0h] [rbp-60h]
  __int64 v26; // [rsp+A8h] [rbp-58h]
  __int64 *v27; // [rsp+B0h] [rbp-50h]
  __int64 v28; // [rsp+B8h] [rbp-48h]
  __int64 *v29; // [rsp+C0h] [rbp-40h]
  __int64 v30; // [rsp+C8h] [rbp-38h]
  __int64 *v31; // [rsp+D0h] [rbp-30h]
  __int64 v32; // [rsp+D8h] [rbp-28h]
  __int64 *v33; // [rsp+E0h] [rbp-20h]
  __int64 v34; // [rsp+E8h] [rbp-18h]
  _BYTE v35[16]; // [rsp+F0h] [rbp-10h] BYREF
  const struct ID2D1PathGeometry **v36; // [rsp+100h] [rbp+0h]
  __int64 v37; // [rsp+108h] [rbp+8h]
  __int64 *v38; // [rsp+110h] [rbp+10h]
  __int64 v39; // [rsp+118h] [rbp+18h]

  *(_QWORD *)this = a3;
  *((_QWORD *)this + 1) = a4;
  if ( (Microsoft_Windows_D2D1EnableBits & 1) != 0 )
  {
    v10 = (__int64)*a4;
    v11 = a3;
    v36 = &v11;
    v38 = &v10;
    v37 = 8;
    v39 = 8;
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)&PathGeometry_Open_Start,
      (_DWORD)a3,
      3,
      (__int64)v35);
  }
  if ( *((_BYTE *)a2 + 108) )
  {
    _InterlockedIncrement((volatile signed __int32 *)a2 + 8);
    if ( *((_BYTE *)a2 + 84) )
    {
      if ( *((_DWORD *)a2 + 20) < *((_DWORD *)a2 + 3) )
      {
        v6 = 214013 * *((_DWORD *)a2 + 22) + 2531011;
        *((_DWORD *)a2 + 22) = v6;
        if ( (signed int)(HIWORD(v6) & 0x7FFF) <= *((_DWORD *)a2 + 11) )
        {
          _InterlockedIncrement((volatile signed __int32 *)a2 + 20);
          if ( (unsigned int)dword_1805DAC58 > 5
            && (qword_1805DAC68 & 0x200000000000LL) != 0
            && (qword_1805DAC70 & 0x200000000000LL) == qword_1805DAC70 )
          {
            v7 = (__int64 *)*((_QWORD *)this + 1);
            v12 = 0x1000000;
            v16 = 0x200000000000LL;
            v34 = 8;
            v8 = *v7;
            v14 = *(_QWORD *)this;
            v33 = &v12;
            v31 = &v13;
            v29 = &v14;
            v27 = &v10;
            v25 = "Open";
            v23 = "IPathGeometry";
            v15[1] = 5;
            v13 = v8;
            v17 = off_1805DAC60;
            LODWORD(v10) = 1;
            v32 = 8;
            v30 = 8;
            v28 = 4;
            v26 = 5;
            v24 = 14;
            v15[0] = 184549376;
            v18 = *(unsigned __int16 *)off_1805DAC60;
            v20 = &unk_1805A68A0;
            v19 = 2;
            v21 = 105;
            v22 = 1;
            LODWORD(v11) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwEventWriteTransfer(RegHandle, v15, 0, 0, 8, &v17);
          }
        }
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180016410  mov     [rsp-8+arg_10], rbx
0x180016415  push    rbp
0x180016416  push    rsi
0x180016417  push    rdi
0x180016418  lea     rbp, [rsp-30h]
0x18001641d  sub     rsp, 130h
0x180016424  mov     rax, cs:__security_cookie
0x18001642b  xor     rax, rsp
0x18001642e  mov     [rbp+40h+var_20], rax
0x180016432  mov     [rcx], r8
0x180016435  mov     rbx, rdx
0x180016438  mov     [rcx+8], r9
0x18001643c  mov     rdi, rcx
0x18001643f  test    byte ptr cs:Microsoft_Windows_D2D1EnableBits, 1
0x180016446  jz      short loc_180016492
0x180016448  mov     rax, [r9]
0x18001644b  lea     rdx, PathGeometry_Open_Start
0x180016452  mov     [rsp+140h+var_110], rax
0x180016457  mov     r9d, 3
0x18001645d  lea     rax, [rsp+140h+var_108]
0x180016462  mov     [rsp+140h+var_108], r8
0x180016467  mov     [rbp+40h+var_40], rax
0x18001646b  lea     rax, [rsp+140h+var_110]
0x180016470  mov     [rbp+40h+var_30], rax
0x180016474  lea     rax, [rbp+40h+var_50]
0x180016478  mov     [rsp+140h+var_120], rax
0x18001647d  mov     [rbp+40h+var_38], 8
0x180016485  mov     [rbp+40h+var_28], 8
0x18001648d  call    McGenEventWrite_EtwEventWriteTransfer
0x180016492  cmp     byte ptr [rbx+6Ch], 0
0x180016496  jz      loc_180016636
0x18001649c  lock inc dword ptr [rbx+20h]
0x1800164a0  cmp     byte ptr [rbx+54h], 0
0x1800164a4  jz      loc_180016636
0x1800164aa  mov     eax, [rbx+0Ch]
0x1800164ad  cmp     [rbx+50h], eax
0x1800164b0  jnb     loc_180016636
0x1800164b6  imul    eax, [rbx+58h], 343FDh
0x1800164bd  add     eax, 269EC3h
0x1800164c2  mov     [rbx+58h], eax
0x1800164c5  shr     eax, 10h
0x1800164c8  and     eax, 7FFFh
0x1800164cd  cmp     eax, [rbx+2Ch]
0x1800164d0  jg      loc_180016636
0x1800164d6  lock inc dword ptr [rbx+50h]
0x1800164da  mov     eax, cs:dword_1805DAC58
0x1800164e0  cmp     eax, 5
0x1800164e3  jbe     loc_180016636
0x1800164e9  mov     rcx, cs:qword_1805DAC70
0x1800164f0  mov     rdx, 200000000000h
0x1800164fa  mov     rax, cs:qword_1805DAC68
0x180016501  test    rdx, rax
0x180016504  jz      loc_180016636
0x18001650a  mov     rax, rcx
0x18001650d  and     rax, rdx
0x180016510  cmp     rax, rcx
0x180016513  jnz     loc_180016636
0x180016519  mov     rax, [rdi+8]
0x18001651d  xor     r9d, r9d
0x180016520  mov     [rsp+140h+var_100], 1000000h
0x180016529  xor     r8d, r8d
0x18001652c  mov     [rsp+140h+var_E0], rdx
0x180016531  lea     rdx, [rsp+140h+var_E8]
0x180016536  mov     [rbp+40h+var_58], 8
0x18001653e  mov     rcx, [rax]
0x180016541  mov     rax, [rdi]
0x180016544  mov     [rsp+140h+var_F0], rax
0x180016549  lea     rax, [rsp+140h+var_100]
0x18001654e  mov     [rbp+40h+var_60], rax
0x180016552  lea     rax, [rsp+140h+var_F8]
0x180016557  mov     [rbp+40h+var_70], rax
0x18001655b  lea     rax, [rsp+140h+var_F0]
0x180016560  mov     [rbp+40h+var_80], rax
0x180016564  lea     rax, [rsp+140h+var_110]
0x180016569  mov     [rbp+40h+var_90], rax
0x18001656d  lea     rax, aOpen; "Open"
0x180016574  mov     [rbp+40h+var_A0], rax
0x180016578  lea     rax, aIpathgeometry; "IPathGeometry"
0x18001657f  mov     [rbp+40h+var_B0], rax
0x180016583  movzx   eax, cs:word_1805A6896
0x18001658a  mov     [rsp+140h+var_E4], eax
0x18001658e  mov     rax, cs:off_1805DAC60
0x180016595  mov     [rsp+140h+var_F8], rcx
0x18001659a  lea     rcx, _TraceLoggingMetadataEnd
0x1800165a1  mov     [rsp+140h+var_D0], rax
0x1800165a6  mov     dword ptr [rsp+140h+var_110], 1
0x1800165ae  mov     [rbp+40h+var_68], 8
0x1800165b6  mov     [rbp+40h+var_78], 8
0x1800165be  mov     [rbp+40h+var_88], 4
0x1800165c6  mov     [rbp+40h+var_98], 5
0x1800165ce  mov     [rbp+40h+var_A8], 0Eh
0x1800165d6  mov     [rsp+140h+var_E8], 0B000000h
0x1800165de  movzx   eax, word ptr [rax]
0x1800165e1  mov     [rsp+140h+var_C8], eax
0x1800165e5  lea     rax, unk_1805A68A0
0x1800165ec  mov     [rbp+40h+var_C0], rax
0x1800165f0  lea     rax, _TraceLoggingMetadata
0x1800165f7  sub     ecx, eax
0x1800165f9  mov     [rsp+140h+var_C4], 2
0x180016601  mov     [rbp+40h+var_B8], 69h ; 'i'
0x180016608  lea     rax, [rsp+140h+var_D0]
0x18001660d  mov     [rbp+40h+var_B4], 1
0x180016614  mov     dword ptr [rsp+140h+var_108], ecx
0x180016618  mov     ecx, dword ptr [rsp+140h+var_108]
0x18001661c  mov     rcx, cs:RegHandle
0x180016623  mov     [rsp+140h+var_118], rax
0x180016628  mov     dword ptr [rsp+140h+var_120], 8
0x180016630  call    cs:__imp_EtwEventWriteTransfer
0x180016636  mov     rax, rdi
0x180016639  mov     rcx, [rbp+40h+var_20]
0x18001663d  xor     rcx, rsp; StackCookie
0x180016640  call    __security_check_cookie
0x180016645  mov     rbx, [rsp+140h+arg_10]
0x18001664d  add     rsp, 130h
0x180016654  pop     rdi
0x180016655  pop     rsi
0x180016656  pop     rbp
0x180016657  retn
```
