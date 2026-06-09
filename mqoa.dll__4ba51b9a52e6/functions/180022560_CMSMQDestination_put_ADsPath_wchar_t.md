# CMSMQDestination::put_ADsPath(wchar_t *)

- ea: `0x180022560`
- end: `0x18002263b`
- name: `?put_ADsPath@CMSMQDestination@@UEAAJPEA_W@Z`
- size: `219`
- prototype: `int(CMSMQDestination *__hidden this, wchar_t *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005430`
- `0x18000cb34`
- `0x180021ed4`
- `0x180022560`
- `0x180029010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800225d2`
- `KERNEL32!LeaveCriticalSection` at `0x1800225d2`
- `OLEAUT32!__imp_SysAllocString` at `0x180022597`
- `OLEAUT32!__imp_SysAllocString` at `0x180022597`
- `OLEAUT32!__imp_SysFreeString` at `0x1800225b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800225ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800225e8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800225f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180022611`
- `OLEAUT32!__imp_SysFreeString` at `0x1800225b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800225ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800225e8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800225f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180022611`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQDestination::put_ADsPath(CMSMQDestination *this, wchar_t *a2)
{
  signed int FormatNameFromADsPath; // ebx
  BSTR v5; // rbx
  OLECHAR *v6; // rdi
  unsigned int ErrorHelper; // ebx
  BSTR bstrString; // [rsp+50h] [rbp+8h] BYREF

  CCriticalSection::Lock((CMSMQDestination *)((char *)this + 80));
  bstrString = 0;
  FormatNameFromADsPath = GetFormatNameFromADsPath(a2, &bstrString);
  if ( FormatNameFromADsPath >= 0 )
  {
    v5 = SysAllocString(a2);
    if ( v5 )
    {
      SysFreeString(*((BSTR *)this + 15));
      *((_QWORD *)this + 15) = v5;
      SysFreeString(*((BSTR *)this + 16));
      *((_QWORD *)this + 16) = 0;
      SysFreeString(*((BSTR *)this + 17));
      *((_QWORD *)this + 17) = bstrString;
      v6 = 0;
      (*(void (__fastcall **)(CMSMQDestination *))(*(_QWORD *)this + 64LL))(this);
      FormatNameFromADsPath = 0;
      goto LABEL_5;
    }
    FormatNameFromADsPath = -2147024882;
  }
  v6 = bstrString;
LABEL_5:
  SysFreeString(0);
  SysFreeString(v6);
  ErrorHelper = CreateErrorHelper(FormatNameFromADsPath, 10);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  return ErrorHelper;
}

```

## disassembly

```asm
0x180022560  push    rbx
0x180022562  push    rbp
0x180022563  push    rsi
0x180022564  push    rdi
0x180022565  sub     rsp, 28h
0x180022569  mov     rdi, rdx
0x18002256c  mov     rsi, rcx
0x18002256f  add     rcx, 50h ; 'P'; this
0x180022573  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180022578  mov     [rsp+48h+bstrString], 0
0x180022581  lea     rdx, [rsp+48h+bstrString]; wchar_t **
0x180022586  mov     rcx, rdi; lpwcsADsPath
0x180022589  call    ?GetFormatNameFromADsPath@@YAJPEB_WPEAPEA_W@Z; GetFormatNameFromADsPath(wchar_t const *,wchar_t * *)
0x18002258e  mov     ebx, eax
0x180022590  test    eax, eax
0x180022592  js      short loc_1800225AA
0x180022594  mov     rcx, rdi; psz
0x180022597  call    cs:__imp_SysAllocString
0x18002259d  mov     rbx, rax
0x1800225a0  test    rax, rax
0x1800225a3  jnz     short loc_1800225E4
0x1800225a5  mov     ebx, 8007000Eh
0x1800225aa  mov     rdi, [rsp+48h+bstrString]
0x1800225af  xor     ecx, ecx; bstrString
0x1800225b1  call    cs:__imp_SysFreeString
0x1800225b7  mov     rcx, rdi; bstrString
0x1800225ba  call    cs:__imp_SysFreeString
0x1800225c0  mov     edx, 0Ah
0x1800225c5  mov     ecx, ebx
0x1800225c7  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x1800225cc  mov     ebx, eax
0x1800225ce  lea     rcx, [rsi+50h]; lpCriticalSection
0x1800225d2  call    cs:__imp_LeaveCriticalSection
0x1800225d8  nop
0x1800225d9  mov     eax, ebx
0x1800225db  add     rsp, 28h
0x1800225df  pop     rdi
0x1800225e0  pop     rsi
0x1800225e1  pop     rbp
0x1800225e2  pop     rbx
0x1800225e3  retn
0x1800225e4  mov     rcx, [rsi+78h]; bstrString
0x1800225e8  call    cs:__imp_SysFreeString
0x1800225ee  mov     [rsi+78h], rbx
0x1800225f2  mov     rcx, [rsi+80h]; bstrString
0x1800225f9  call    cs:__imp_SysFreeString
0x1800225ff  mov     qword ptr [rsi+80h], 0
0x18002260a  mov     rcx, [rsi+88h]; bstrString
0x180022611  call    cs:__imp_SysFreeString
0x180022617  mov     rax, [rsp+48h+bstrString]
0x18002261c  mov     [rsi+88h], rax
0x180022623  xor     edi, edi
0x180022625  mov     rax, [rsi]
0x180022628  mov     rcx, rsi
0x18002262b  mov     rax, [rax+40h]
0x18002262f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022634  xor     ebx, ebx
0x180022636  jmp     loc_1800225AF
```
