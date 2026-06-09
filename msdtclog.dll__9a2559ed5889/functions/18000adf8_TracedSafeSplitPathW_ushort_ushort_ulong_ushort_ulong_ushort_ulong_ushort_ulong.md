# TracedSafeSplitPathW(ushort *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *,ulong)

- ea: `0x18000adf8`
- end: `0x18000afa2`
- name: `?TracedSafeSplitPathW@@YAJPEAG0K0K0K0K@Z`
- size: `426`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, __int64, unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000bc44`
- `0x18000c350`

## callees

- `0x18000ac98`
- `0x18000ad1c`
- `0x18000adf8`
- `0x18000d998`
- `0x18000dc8c`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000ae71`
- `msvcrt!wcsrchr` at `0x18000aeb0`
- `msvcrt!wcsrchr` at `0x18000ae71`
- `msvcrt!wcsrchr` at `0x18000aeb0`
- `msvcrt!iswalpha` at `0x18000ae18`
- `msvcrt!iswalpha` at `0x18000ae18`

## string_xrefs

- `0x18000af08`: `com\complus\dtc\inc\tracedstrsafe.h`
- `0x18000af30`: `com\complus\dtc\inc\tracedstrsafe.h`
- `0x18000af58`: `com\complus\dtc\inc\tracedstrsafe.h`
- `0x18000af80`: `com\complus\dtc\inc\tracedstrsafe.h`
- `0x18000af87`: `failed in TracedStringCchCopyW`
- `0x18000af95`: `failed in TracedStringCchCopyW`
- `0x18000af0f`: `failed in TracedStringCchCopyNW`
- `0x18000af37`: `failed in TracedStringCchCopyNW`
- `0x18000af5f`: `failed in TracedStringCchCopyNW`
- `0x18000af1d`: `failed in TracedStringCchCopyNW`
- `0x18000af45`: `failed in TracedStringCchCopyNW`
- `0x18000af6d`: `failed in TracedStringCchCopyNW`

## pseudocode

```c
__int64 __fastcall TracedSafeSplitPathW(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 *a6)
{
  unsigned __int16 *v9; // rdi
  int v10; // eax
  const wchar_t *v11; // rcx
  unsigned __int64 v12; // rbx
  wchar_t *v13; // rax
  int v14; // eax
  wchar_t *v15; // rbx
  wchar_t *v16; // rax
  int v17; // eax
  int v18; // eax

  if ( !a1 )
    return 2147942487LL;
  if ( !iswalpha(*a1) )
    return 2147942487LL;
  if ( a1[1] != 58 )
    return 2147942487LL;
  v9 = a1 + 2;
  if ( a1[2] != 92 )
    return 2147942487LL;
  if ( a2 )
  {
    v10 = StringCchCopyNW(a2, 3u, a1, 2u);
    if ( v10 < 0 )
    {
      TraceFile(v10, "failed in TracedStringCchCopyNW", "com\\complus\\dtc\\inc\\tracedstrsafe.h", 0xCDu);
      DtcInternalErrorW(L"failed in TracedStringCchCopyNW");
    }
  }
  v11 = a1 + 3;
  v12 = 1;
  v13 = wcsrchr(v11, 0x5Cu);
  if ( v13 )
    v12 = v13 - v9 + 1;
  if ( a4 )
  {
    v14 = StringCchCopyNW(a4, a5, v9, v12);
    if ( v14 < 0 )
    {
      TraceFile(v14, "failed in TracedStringCchCopyNW", "com\\complus\\dtc\\inc\\tracedstrsafe.h", 0xCDu);
      DtcInternalErrorW(L"failed in TracedStringCchCopyNW");
    }
  }
  v15 = &v9[v12];
  v16 = wcsrchr(v15, 0x2Eu);
  if ( a6 )
  {
    if ( v16 )
    {
      v17 = StringCchCopyNW(a6, 0x104u, v15, v16 - v15);
      if ( v17 < 0 )
      {
        TraceFile(v17, "failed in TracedStringCchCopyNW", "com\\complus\\dtc\\inc\\tracedstrsafe.h", 0xCDu);
        DtcInternalErrorW(L"failed in TracedStringCchCopyNW");
      }
    }
    else
    {
      v18 = StringCchCopyW(a6, 0x104u, v15);
      if ( v18 < 0 )
      {
        TraceFile(v18, "failed in TracedStringCchCopyW", "com\\complus\\dtc\\inc\\tracedstrsafe.h", 0x84u);
        DtcInternalErrorW(L"failed in TracedStringCchCopyW");
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000adf8  push    rbx
0x18000adfa  push    rbp
0x18000adfb  push    rsi
0x18000adfc  push    rdi
0x18000adfd  push    r14
0x18000adff  sub     rsp, 20h
0x18000ae03  mov     rbp, r9
0x18000ae06  mov     rsi, rdx
0x18000ae09  mov     rbx, rcx
0x18000ae0c  test    rcx, rcx
0x18000ae0f  jz      loc_18000AEF2
0x18000ae15  movzx   ecx, word ptr [rcx]; C
0x18000ae18  call    cs:__imp_iswalpha
0x18000ae1e  test    eax, eax
0x18000ae20  jz      loc_18000AEF2
0x18000ae26  cmp     word ptr [rbx+2], 3Ah ; ':'
0x18000ae2b  jnz     loc_18000AEF2
0x18000ae31  lea     rdi, [rbx+4]
0x18000ae35  mov     r14d, 5Ch ; '\'
0x18000ae3b  cmp     [rdi], r14w
0x18000ae3f  jnz     loc_18000AEF2
0x18000ae45  test    rsi, rsi
0x18000ae48  jz      short loc_18000AE65
0x18000ae4a  lea     r9d, [r14-5Ah]; unsigned __int64
0x18000ae4e  mov     r8, rbx; unsigned __int16 *
0x18000ae51  lea     edx, [r14-59h]; unsigned __int64
0x18000ae55  mov     rcx, rsi; unsigned __int16 *
0x18000ae58  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000ae5d  test    eax, eax
0x18000ae5f  js      loc_18000AF02
0x18000ae65  mov     edx, r14d; Ch
0x18000ae68  lea     rcx, [rdi+2]; Str
0x18000ae6c  mov     ebx, 1
0x18000ae71  call    cs:__imp_wcsrchr
0x18000ae77  test    rax, rax
0x18000ae7a  jz      short loc_18000AE85
0x18000ae7c  sub     rax, rdi
0x18000ae7f  sar     rax, 1
0x18000ae82  add     rbx, rax
0x18000ae85  test    rbp, rbp
0x18000ae88  jz      short loc_18000AEA4
0x18000ae8a  mov     edx, [rsp+48h+arg_20]; unsigned __int64
0x18000ae8e  mov     r9, rbx; unsigned __int64
0x18000ae91  mov     r8, rdi; unsigned __int16 *
0x18000ae94  mov     rcx, rbp; unsigned __int16 *
0x18000ae97  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000ae9c  test    eax, eax
0x18000ae9e  js      loc_18000AF2A
0x18000aea4  lea     rbx, [rdi+rbx*2]
0x18000aea8  mov     edx, 2Eh ; '.'; Ch
0x18000aead  mov     rcx, rbx; Str
0x18000aeb0  call    cs:__imp_wcsrchr
0x18000aeb6  mov     rcx, [rsp+48h+arg_28]; unsigned __int16 *
0x18000aebb  test    rcx, rcx
0x18000aebe  jz      short loc_18000AEEE
0x18000aec0  mov     r8, rbx; unsigned __int16 *
0x18000aec3  mov     edx, 104h; unsigned __int64
0x18000aec8  test    rax, rax
0x18000aecb  jz      short loc_18000AEE1
0x18000aecd  sub     rax, rbx
0x18000aed0  sar     rax, 1
0x18000aed3  mov     r9, rax; unsigned __int64
0x18000aed6  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000aedb  test    eax, eax
0x18000aedd  js      short loc_18000AF52
0x18000aedf  jmp     short loc_18000AEEE
0x18000aee1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000aee6  test    eax, eax
0x18000aee8  js      loc_18000AF7A
0x18000aeee  xor     eax, eax
0x18000aef0  jmp     short loc_18000AEF7
0x18000aef2  mov     eax, 80070057h
0x18000aef7  add     rsp, 20h
0x18000aefb  pop     r14
0x18000aefd  pop     rdi
0x18000aefe  pop     rsi
0x18000aeff  pop     rbp
0x18000af00  pop     rbx
0x18000af01  retn
0x18000af02  mov     r9d, 0CDh; unsigned int
0x18000af08  lea     r8, aComComplusDtcI; "com\\complus\\dtc\\inc\\tracedstrsafe.h"
0x18000af0f  lea     rdx, aFailedInTraced_7; "failed in TracedStringCchCopyNW"
0x18000af16  mov     ecx, eax; int
0x18000af18  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000af1d  lea     rcx, aFailedInTraced_8; "failed in TracedStringCchCopyNW"
0x18000af24  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18000af2a  mov     r9d, 0CDh; unsigned int
0x18000af30  lea     r8, aComComplusDtcI; "com\\complus\\dtc\\inc\\tracedstrsafe.h"
0x18000af37  lea     rdx, aFailedInTraced_7; "failed in TracedStringCchCopyNW"
0x18000af3e  mov     ecx, eax; int
0x18000af40  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000af45  lea     rcx, aFailedInTraced_8; "failed in TracedStringCchCopyNW"
0x18000af4c  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18000af52  mov     r9d, 0CDh; unsigned int
0x18000af58  lea     r8, aComComplusDtcI; "com\\complus\\dtc\\inc\\tracedstrsafe.h"
0x18000af5f  lea     rdx, aFailedInTraced_7; "failed in TracedStringCchCopyNW"
0x18000af66  mov     ecx, eax; int
0x18000af68  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000af6d  lea     rcx, aFailedInTraced_8; "failed in TracedStringCchCopyNW"
0x18000af74  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18000af7a  mov     r9d, 84h; unsigned int
0x18000af80  lea     r8, aComComplusDtcI; "com\\complus\\dtc\\inc\\tracedstrsafe.h"
0x18000af87  lea     rdx, aFailedInTraced_3; "failed in TracedStringCchCopyW"
0x18000af8e  mov     ecx, eax; int
0x18000af90  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000af95  lea     rcx, aFailedInTraced_0; "failed in TracedStringCchCopyW"
0x18000af9c  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
