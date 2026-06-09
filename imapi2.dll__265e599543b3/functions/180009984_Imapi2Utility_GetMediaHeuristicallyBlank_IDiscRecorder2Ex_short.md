# Imapi2Utility::GetMediaHeuristicallyBlank(IDiscRecorder2Ex *,short *)

- ea: `0x180009984`
- end: `0x180009aaf`
- name: `?GetMediaHeuristicallyBlank@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAF@Z`
- size: `299`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IDiscRecorder2Ex *, __int16 *)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800095c0`
- `0x180027990`
- `0x180031770`
- `0x18003b080`

## callees

- `0x180009984`
- `0x180009ab8`
- `0x180009b80`
- `0x18000a8ac`
- `0x180044254`
- `0x180046708`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::GetMediaHeuristicallyBlank(
        struct IDiscRecorder2Ex *this,
        struct IDiscRecorder2Ex *a2,
        __int16 *a3)
{
  int MediaPhysicallyBlank; // eax
  unsigned __int64 v6; // r8
  int CurrentPhysicalMediaType; // eax
  int v8; // ecx
  BOOL v9; // eax
  unsigned int *v10; // r9
  int DataDisc; // ecx
  void *v13; // [rsp+28h] [rbp-18h]
  struct IDiscRecorder2Ex v14; // [rsp+30h] [rbp-10h] BYREF
  IDiscRecorder2Ex v15; // [rsp+70h] [rbp+30h] BYREF
  struct IDiscRecorder2Ex v16; // [rsp+78h] [rbp+38h] BYREF

  LODWORD(v14.lpVtbl) = 0;
  LOWORD(v15.lpVtbl) = 0;
  LODWORD(v16.lpVtbl) = 0;
  MediaPhysicallyBlank = Imapi2Utility::GetMediaPhysicallyBlank(this, &v15, a3);
  v6 = (unsigned int)MediaPhysicallyBlank;
  if ( MediaPhysicallyBlank >= 0 )
  {
    CurrentPhysicalMediaType = Imapi2Utility::GetCurrentPhysicalMediaType(
                                 this,
                                 &v16,
                                 (enum _IMAPI_MEDIA_PHYSICAL_TYPE *)(unsigned int)MediaPhysicallyBlank);
    v6 = (unsigned int)CurrentPhysicalMediaType;
    if ( CurrentPhysicalMediaType >= 0 && LOWORD(v15.lpVtbl) == 0xFFFF )
      goto LABEL_17;
  }
  if ( LODWORD(v16.lpVtbl) <= 0x12 )
  {
    v8 = 397150;
    if ( _bittest(&v8, (unsigned int)v16.lpVtbl) )
    {
      v9 = LOWORD(v15.lpVtbl) != 0;
      if ( (v6 & 0x80000000) != 0LL )
        return (unsigned int)v6;
LABEL_15:
      if ( !v9 )
      {
        LOWORD(a2->lpVtbl) = 0;
        return (unsigned int)v6;
      }
LABEL_17:
      LOWORD(a2->lpVtbl) = -1;
      return (unsigned int)v6;
    }
  }
  if ( (v6 & 0x80000000) == 0LL )
  {
    LODWORD(v15.lpVtbl) = -1;
    LODWORD(v6) = Imapi2Utility::GetMediaFormatStatus(
                    (Imapi2Utility *)this,
                    &v15,
                    (enum Imapi2Utility::_FORMAT_STATUS *)v6);
    if ( (v6 & 0x80000000) == 0LL )
    {
      if ( LODWORD(v15.lpVtbl) == 1 )
        goto LABEL_17;
      LODWORD(v15.lpVtbl) = 0;
      LODWORD(v6) = Imapi2Utility::ReadMediaCapacity((Imapi2Utility *)this, &v14, (unsigned int *)&v15, v10);
      if ( (v6 & 0x80000000) == 0LL )
      {
        LODWORD(v13) = 0;
        DataDisc = Imapi2Utility::ReadDataDisc(
                     (Imapi2Utility *)this,
                     0,
                     0x200000u / LODWORD(v14.lpVtbl),
                     (unsigned int *)Imapi2Utility::HeuristicBlankValidatorFunction,
                     0,
                     v13);
        v9 = 0;
        if ( DataDisc != -1062600697 )
          LOBYTE(v9) = DataDisc >= 0;
        LODWORD(v6) = 0;
        goto LABEL_15;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009984  mov     [rsp-18h+arg_0], rbx
0x180009989  mov     [rsp-18h+arg_8], rsi
0x18000998e  push    rbp
0x18000998f  push    r14
0x180009991  push    r15
0x180009993  mov     rbp, rsp
0x180009996  sub     rsp, 40h
0x18000999a  xor     r14d, r14d
0x18000999d  mov     rsi, rdx
0x1800099a0  lea     rdx, [rbp+arg_10]; struct IDiscRecorder2Ex *
0x1800099a4  mov     dword ptr [rbp+var_10.lpVtbl], r14d
0x1800099a8  mov     word ptr [rbp+arg_10.lpVtbl], r14w
0x1800099ad  mov     rbx, rcx
0x1800099b0  mov     dword ptr [rbp+arg_18.lpVtbl], r14d
0x1800099b4  call    ?GetMediaPhysicallyBlank@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAF@Z; Imapi2Utility::GetMediaPhysicallyBlank(IDiscRecorder2Ex *,short *)
0x1800099b9  or      r15d, 0FFFFFFFFh
0x1800099bd  mov     r8d, eax; enum _IMAPI_MEDIA_PHYSICAL_TYPE *
0x1800099c0  test    eax, eax
0x1800099c2  js      short loc_1800099E2
0x1800099c4  lea     rdx, [rbp+arg_18]; struct IDiscRecorder2Ex *
0x1800099c8  mov     rcx, rbx; this
0x1800099cb  call    ?GetCurrentPhysicalMediaType@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAW4_IMAPI_MEDIA_PHYSICAL_TYPE@@@Z; Imapi2Utility::GetCurrentPhysicalMediaType(IDiscRecorder2Ex *,_IMAPI_MEDIA_PHYSICAL_TYPE *)
0x1800099d0  mov     r8d, eax; enum Imapi2Utility::_FORMAT_STATUS *
0x1800099d3  test    eax, eax
0x1800099d5  js      short loc_1800099E2
0x1800099d7  cmp     word ptr [rbp+arg_10.lpVtbl], r15w
0x1800099dc  jz      loc_180009A94
0x1800099e2  mov     eax, dword ptr [rbp+arg_18.lpVtbl]
0x1800099e5  cmp     eax, 12h
0x1800099e8  ja      short loc_180009A0D
0x1800099ea  mov     ecx, 60F5Eh
0x1800099ef  bt      ecx, eax
0x1800099f2  jnb     short loc_180009A0D
0x1800099f4  cmp     word ptr [rbp+arg_10.lpVtbl], r14w
0x1800099f9  mov     eax, r14d
0x1800099fc  setnz   al
0x1800099ff  test    r8d, r8d
0x180009a02  jns     loc_180009A8A
0x180009a08  jmp     loc_180009A98
0x180009a0d  test    r8d, r8d
0x180009a10  js      loc_180009A98
0x180009a16  lea     rdx, [rbp+arg_10]; struct IDiscRecorder2Ex *
0x180009a1a  mov     dword ptr [rbp+arg_10.lpVtbl], r15d
0x180009a1e  mov     rcx, rbx; this
0x180009a21  call    ?GetMediaFormatStatus@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAW4_FORMAT_STATUS@1@@Z; Imapi2Utility::GetMediaFormatStatus(IDiscRecorder2Ex *,Imapi2Utility::_FORMAT_STATUS *)
0x180009a26  mov     r8d, eax
0x180009a29  test    eax, eax
0x180009a2b  js      short loc_180009A98
0x180009a2d  cmp     dword ptr [rbp+arg_10.lpVtbl], 1
0x180009a31  jz      short loc_180009A94
0x180009a33  lea     r8, [rbp+arg_10]; unsigned int *
0x180009a37  mov     dword ptr [rbp+arg_10.lpVtbl], r14d
0x180009a3b  lea     rdx, [rbp+var_10]; struct IDiscRecorder2Ex *
0x180009a3f  mov     rcx, rbx; this
0x180009a42  call    ?ReadMediaCapacity@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAK1@Z; Imapi2Utility::ReadMediaCapacity(IDiscRecorder2Ex *,ulong *,ulong *)
0x180009a47  mov     r8d, eax
0x180009a4a  test    eax, eax
0x180009a4c  js      short loc_180009A98
0x180009a4e  xor     edx, edx
0x180009a50  mov     dword ptr [rsp+40h+var_18], r14d; void *
0x180009a55  mov     eax, 200000h
0x180009a5a  mov     [rsp+40h+var_20], r14; int (*)(unsigned __int8 *, unsigned int, unsigned int, unsigned int, void *, unsigned int)
0x180009a5f  div     dword ptr [rbp+var_10.lpVtbl]
0x180009a62  lea     r9, ?HeuristicBlankValidatorFunction@Imapi2Utility@@YAJPEAEKKKPEAXK@Z; unsigned int
0x180009a69  xor     edx, edx; struct IDiscRecorder2Ex *
0x180009a6b  mov     r8d, eax; unsigned int
0x180009a6e  mov     rcx, rbx; this
0x180009a71  call    ?ReadDataDisc@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@KKP6AJPEAEKKKPEAXK@Z2K@Z; Imapi2Utility::ReadDataDisc(IDiscRecorder2Ex *,ulong,ulong,long (*)(uchar *,ulong,ulong,ulong,void *,ulong),void *,ulong)
0x180009a76  mov     ecx, eax
0x180009a78  cmp     eax, 0C0AA0007h
0x180009a7d  mov     eax, r14d
0x180009a80  jz      short loc_180009A87
0x180009a82  test    ecx, ecx
0x180009a84  setns   al
0x180009a87  mov     r8d, r14d
0x180009a8a  test    eax, eax
0x180009a8c  jnz     short loc_180009A94
0x180009a8e  mov     [rsi], r14w
0x180009a92  jmp     short loc_180009A98
0x180009a94  mov     [rsi], r15w
0x180009a98  mov     rbx, [rsp+40h+arg_0]
0x180009a9d  mov     eax, r8d
0x180009aa0  mov     rsi, [rsp+40h+arg_8]
0x180009aa5  add     rsp, 40h
0x180009aa9  pop     r15
0x180009aab  pop     r14
0x180009aad  pop     rbp
0x180009aae  retn
```
