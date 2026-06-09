# myCRLNumber(char const *,_CRL_CONTEXT const *)

- ea: `0x18001aa28`
- end: `0x18001ab11`
- name: `?myCRLNumber@@YAPEAGPEBDPEBU_CRL_CONTEXT@@@Z`
- size: `233`
- prototype: `unsigned __int16 *__fastcall(const char *, const struct _CRL_CONTEXT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180019b68`
- `0x18001a708`

## callees

- `0x180008400`
- `0x180012450`
- `0x18001aa28`
- `0x18001da80`
- `0x18001e080`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ab01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ab01`
- `CRYPT32!CertFindExtension` at `0x18001aa5c`
- `CRYPT32!CertFindExtension` at `0x18001aa5c`

## pseudocode

```c
unsigned __int16 *__fastcall myCRLNumber(const char *a1, const struct _CRL_CONTEXT *a2)
{
  PCRL_INFO pCrlInfo; // rdx
  PCERT_EXTENSION Extension; // rax
  int v4; // edx
  unsigned int v5; // ecx
  unsigned __int16 *v7; // [rsp+60h] [rbp+18h]

  pCrlInfo = a2->pCrlInfo;
  v7 = 0;
  Extension = CertFindExtension("2.5.29.20", pCrlInfo->cExtension, pCrlInfo->rgExtension);
  if ( Extension )
  {
    if ( (unsigned int)myDecodeObjectEx(1, 28, Extension->Value.pbData, Extension->Value.cbData, 0) )
    {
      v4 = -2147024883;
      v5 = 293077411;
    }
    else
    {
      v4 = myHLastError();
      v5 = 292749731;
    }
  }
  else
  {
    v4 = -2147024894;
    v5 = 291963299;
  }
  CSPrintErrorLineFile(v5, v4);
  return v7;
}

```

## disassembly

```asm
0x18001aa28  mov     rax, rsp
0x18001aa2b  mov     [rax+8], rcx
0x18001aa2f  sub     rsp, 48h
0x18001aa33  mov     rdx, [rdx+18h]
0x18001aa37  lea     rcx, a252920; "2.5.29.20"
0x18001aa3e  mov     qword ptr [rax+10h], 0
0x18001aa46  mov     dword ptr [rax+8], 0
0x18001aa4d  mov     qword ptr [rax+18h], 0
0x18001aa55  mov     r8, [rdx+58h]; rgExtensions
0x18001aa59  mov     edx, [rdx+50h]; cExtensions
0x18001aa5c  call    cs:__imp_CertFindExtension
0x18001aa62  test    rax, rax
0x18001aa65  jnz     short loc_18001AA73
0x18001aa67  mov     edx, 80070002h
0x18001aa6c  mov     ecx, 116701A3h
0x18001aa71  jmp     short loc_18001AAF2
0x18001aa73  mov     r9d, [rax+10h]
0x18001aa77  lea     rcx, [rsp+48h+arg_0]
0x18001aa7c  mov     r8, [rax+18h]
0x18001aa80  mov     edx, 1Ch
0x18001aa85  mov     [rsp+48h+var_10], rcx
0x18001aa8a  lea     rcx, [rsp+48h+hMem]
0x18001aa8f  mov     [rsp+48h+var_18], rcx
0x18001aa94  mov     [rsp+48h+var_28], 0
0x18001aa9c  lea     ecx, [rdx-1Bh]
0x18001aa9f  call    ?myDecodeObjectEx@@YAHKPEBDPEBEKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x18001aaa4  test    eax, eax
0x18001aaa6  jnz     short loc_18001AAB6
0x18001aaa8  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001aaad  mov     edx, eax
0x18001aaaf  mov     ecx, 117301A3h
0x18001aab4  jmp     short loc_18001AAF2
0x18001aab6  mov     rax, [rsp+48h+hMem]
0x18001aabb  test    rax, rax
0x18001aabe  jz      short loc_18001AAE8
0x18001aac0  mov     r8, [rax+8]; unsigned __int8 *
0x18001aac4  test    r8, r8
0x18001aac7  jz      short loc_18001AAE8
0x18001aac9  mov     edx, [rax]; unsigned int
0x18001aacb  test    edx, edx
0x18001aacd  jz      short loc_18001AAE8
0x18001aacf  lea     r9, [rsp+48h+arg_10]; unsigned __int16 **
0x18001aad4  xor     ecx, ecx; unsigned int
0x18001aad6  call    ?MultiByteIntegerToBstr@@YAJKKPEBEPEAPEAG@Z; MultiByteIntegerToBstr(ulong,ulong,uchar const *,ushort * *)
0x18001aadb  test    eax, eax
0x18001aadd  jz      short loc_18001AAF7
0x18001aadf  mov     edx, eax
0x18001aae1  mov     ecx, 118001A3h
0x18001aae6  jmp     short loc_18001AAF2
0x18001aae8  mov     edx, 8007000Dh; int
0x18001aaed  mov     ecx, 117801A3h; unsigned int
0x18001aaf2  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001aaf7  mov     rcx, [rsp+48h+hMem]; hMem
0x18001aafc  test    rcx, rcx
0x18001aaff  jz      short loc_18001AB07
0x18001ab01  call    cs:__imp_LocalFree
0x18001ab07  mov     rax, [rsp+48h+arg_10]
0x18001ab0c  add     rsp, 48h
0x18001ab10  retn
```
