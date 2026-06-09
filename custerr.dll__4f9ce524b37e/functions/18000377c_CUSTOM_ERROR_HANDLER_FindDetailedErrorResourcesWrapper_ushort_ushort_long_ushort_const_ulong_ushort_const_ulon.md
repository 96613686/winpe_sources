# CUSTOM_ERROR_HANDLER::FindDetailedErrorResourcesWrapper(ushort,ushort,long,ushort const * *,ulong *,ushort const * *,ulong *,ushort const * *,ulong *,ushort const * *,ulong *,ushort const * *,ulong *)

- ea: `0x18000377c`
- end: `0x1800038ad`
- name: `?FindDetailedErrorResourcesWrapper@CUSTOM_ERROR_HANDLER@@AEAAJGGJPEAPEBGPEAK01010101@Z`
- size: `305`
- prototype: `__int64 __fastcall(CUSTOM_ERROR_HANDLER *__hidden this, unsigned __int16, unsigned __int16, int, const unsigned __int16 **, unsigned int *, const unsigned __int16 **, unsigned int *, const unsigned __int16 **, unsigned int *, const unsigned __int16 **, unsigned int *, const unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005988`

## callees

- `0x180002c88`
- `0x18000377c`

## import_xrefs

- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180003801`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x18000382a`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x18000384f`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180003874`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180003899`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180003801`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x18000382a`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x18000384f`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180003874`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180003899`

## pseudocode

```c
int __fastcall CUSTOM_ERROR_HANDLER::FindDetailedErrorResourcesWrapper(
        const char **this,
        unsigned __int16 a2,
        unsigned __int16 a3,
        int a4,
        const unsigned __int16 **a5,
        unsigned int *a6,
        const unsigned __int16 **a7,
        unsigned int *a8,
        const unsigned __int16 **a9,
        unsigned int *a10,
        const unsigned __int16 **a11,
        unsigned int *a12,
        const unsigned __int16 **a13,
        unsigned int *a14)
{
  int result; // eax
  unsigned int v16; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v17; // [rsp+54h] [rbp-1Ch] BYREF
  unsigned int v18; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v19; // [rsp+5Ch] [rbp-14h] BYREF
  unsigned int v20[4]; // [rsp+60h] [rbp-10h] BYREF

  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20[0] = 0;
  result = CUSTOM_ERROR_HANDLER::FindDetailedErrorResources(
             (CUSTOM_ERROR_HANDLER *)this,
             a2,
             a3,
             a4,
             &v16,
             &v17,
             &v18,
             &v19,
             v20);
  if ( result >= 0 )
  {
    result = LANG_STRING::GetString((LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString, v16, this[4], a5, a6);
    if ( result >= 0 )
    {
      result = LANG_STRING::GetString((LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString, v17, this[4], a7, a8);
      if ( result >= 0 )
      {
        result = LANG_STRING::GetString((LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString, v18, this[4], a9, a10);
        if ( result >= 0 )
        {
          result = LANG_STRING::GetString((LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString, v19, this[4], a11, a12);
          if ( result >= 0 )
            return LANG_STRING::GetString(
                     (LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString,
                     v20[0],
                     this[4],
                     a13,
                     a14);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000377c  mov     r11, rsp
0x18000377f  mov     [r11+8], rbx
0x180003783  push    rbp
0x180003784  mov     rbp, rsp
0x180003787  sub     rsp, 70h
0x18000378b  lea     rax, [rbp+var_10]
0x18000378f  mov     [rbp+var_20], 0
0x180003796  mov     [r11-38h], rax
0x18000379a  mov     rbx, rcx
0x18000379d  lea     rax, [rbp+var_14]
0x1800037a1  mov     [rbp+var_1C], 0
0x1800037a8  mov     [r11-40h], rax
0x1800037ac  lea     rax, [rbp+var_18]
0x1800037b0  mov     [r11-48h], rax
0x1800037b4  lea     rax, [rbp+var_1C]
0x1800037b8  mov     [r11-50h], rax
0x1800037bc  lea     rax, [rbp+var_20]
0x1800037c0  mov     [r11-58h], rax
0x1800037c4  mov     [rbp+var_18], 0
0x1800037cb  mov     [rbp+var_14], 0
0x1800037d2  mov     [rbp+var_10], 0
0x1800037d9  call    ?FindDetailedErrorResources@CUSTOM_ERROR_HANDLER@@AEAAJGGJPEAI0000@Z; CUSTOM_ERROR_HANDLER::FindDetailedErrorResources(ushort,ushort,long,uint *,uint *,uint *,uint *,uint *)
0x1800037de  test    eax, eax
0x1800037e0  js      loc_18000389F
0x1800037e6  mov     rax, [rbp+arg_28]
0x1800037ea  mov     r9, [rbp+arg_20]
0x1800037ee  mov     r8, [rbx+20h]
0x1800037f2  mov     edx, [rbp+var_20]
0x1800037f5  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x1800037fc  mov     [rsp+70h+var_50], rax
0x180003801  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x180003807  test    eax, eax
0x180003809  js      loc_18000389F
0x18000380f  mov     rax, [rbp+arg_38]
0x180003813  mov     r9, [rbp+arg_30]
0x180003817  mov     r8, [rbx+20h]
0x18000381b  mov     edx, [rbp+var_1C]
0x18000381e  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x180003825  mov     [rsp+70h+var_50], rax
0x18000382a  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x180003830  test    eax, eax
0x180003832  js      short loc_18000389F
0x180003834  mov     rax, [rbp+arg_48]
0x180003838  mov     r9, [rbp+arg_40]
0x18000383c  mov     r8, [rbx+20h]
0x180003840  mov     edx, [rbp+var_18]
0x180003843  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x18000384a  mov     [rsp+70h+var_50], rax
0x18000384f  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x180003855  test    eax, eax
0x180003857  js      short loc_18000389F
0x180003859  mov     rax, [rbp+arg_58]
0x18000385d  mov     r9, [rbp+arg_50]
0x180003861  mov     r8, [rbx+20h]
0x180003865  mov     edx, [rbp+var_14]
0x180003868  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x18000386f  mov     [rsp+70h+var_50], rax
0x180003874  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x18000387a  test    eax, eax
0x18000387c  js      short loc_18000389F
0x18000387e  mov     rax, [rbp+arg_68]
0x180003882  mov     r9, [rbp+arg_60]
0x180003886  mov     r8, [rbx+20h]
0x18000388a  mov     edx, [rbp+var_10]
0x18000388d  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x180003894  mov     [rsp+70h+var_50], rax
0x180003899  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x18000389f  mov     rbx, [rsp+70h+arg_0]
0x1800038a7  add     rsp, 70h
0x1800038ab  pop     rbp
0x1800038ac  retn
```
