# CMSMQDestination::put_PathName(wchar_t *)

- ea: `0x180022820`
- end: `0x1800228fb`
- name: `?put_PathName@CMSMQDestination@@UEAAJPEA_W@Z`
- size: `219`
- prototype: `int(CMSMQDestination *__hidden this, wchar_t *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005430`
- `0x18000cb34`
- `0x1800220b4`
- `0x180022820`
- `0x180029010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180022892`
- `KERNEL32!LeaveCriticalSection` at `0x180022892`
- `OLEAUT32!__imp_SysAllocString` at `0x180022857`
- `OLEAUT32!__imp_SysAllocString` at `0x180022857`
- `OLEAUT32!__imp_SysFreeString` at `0x180022871`
- `OLEAUT32!__imp_SysFreeString` at `0x18002287a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800228ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800228bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800228d1`
- `OLEAUT32!__imp_SysFreeString` at `0x180022871`
- `OLEAUT32!__imp_SysFreeString` at `0x18002287a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800228ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800228bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800228d1`

## pseudocode

```c
__int64 __fastcall CMSMQDestination::put_PathName(CMSMQDestination *this, wchar_t *a2)
{
  signed int FormatNameFromPathName; // ebx
  BSTR v5; // rbx
  OLECHAR *v6; // rdi
  unsigned int ErrorHelper; // ebx
  BSTR bstrString; // [rsp+50h] [rbp+8h] BYREF

  CCriticalSection::Lock((CMSMQDestination *)((char *)this + 80));
  bstrString = 0;
  FormatNameFromPathName = GetFormatNameFromPathName(a2, &bstrString);
  if ( FormatNameFromPathName >= 0 )
  {
    v5 = SysAllocString(a2);
    if ( v5 )
    {
      SysFreeString(*((BSTR *)this + 16));
      *((_QWORD *)this + 16) = v5;
      SysFreeString(*((BSTR *)this + 15));
      *((_QWORD *)this + 15) = 0;
      SysFreeString(*((BSTR *)this + 17));
      *((_QWORD *)this + 17) = bstrString;
      v6 = 0;
      (*(void (__fastcall **)(CMSMQDestination *))(*(_QWORD *)this + 64LL))(this);
      FormatNameFromPathName = 0;
      goto LABEL_5;
    }
    FormatNameFromPathName = -2147024882;
  }
  v6 = bstrString;
LABEL_5:
  SysFreeString(0);
  SysFreeString(v6);
  ErrorHelper = CreateErrorHelper(FormatNameFromPathName, 10);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  return ErrorHelper;
}

```

## disassembly

```asm
0x180022820  push    rbx
0x180022822  push    rbp
0x180022823  push    rsi
0x180022824  push    rdi
0x180022825  sub     rsp, 28h
0x180022829  mov     rdi, rdx
0x18002282c  mov     rsi, rcx
0x18002282f  add     rcx, 50h ; 'P'; this
0x180022833  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180022838  mov     [rsp+48h+bstrString], 0
0x180022841  lea     rdx, [rsp+48h+bstrString]; wchar_t **
0x180022846  mov     rcx, rdi; lpwcsPathName
0x180022849  call    ?GetFormatNameFromPathName@@YAJPEB_WPEAPEA_W@Z; GetFormatNameFromPathName(wchar_t const *,wchar_t * *)
0x18002284e  mov     ebx, eax
0x180022850  test    eax, eax
0x180022852  js      short loc_18002286A
0x180022854  mov     rcx, rdi; psz
0x180022857  call    cs:__imp_SysAllocString
0x18002285d  mov     rbx, rax
0x180022860  test    rax, rax
0x180022863  jnz     short loc_1800228A4
0x180022865  mov     ebx, 8007000Eh
0x18002286a  mov     rdi, [rsp+48h+bstrString]
0x18002286f  xor     ecx, ecx; bstrString
0x180022871  call    cs:__imp_SysFreeString
0x180022877  mov     rcx, rdi; bstrString
0x18002287a  call    cs:__imp_SysFreeString
0x180022880  mov     edx, 0Ah
0x180022885  mov     ecx, ebx
0x180022887  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18002288c  mov     ebx, eax
0x18002288e  lea     rcx, [rsi+50h]; lpCriticalSection
0x180022892  call    cs:__imp_LeaveCriticalSection
0x180022898  nop
0x180022899  mov     eax, ebx
0x18002289b  add     rsp, 28h
0x18002289f  pop     rdi
0x1800228a0  pop     rsi
0x1800228a1  pop     rbp
0x1800228a2  pop     rbx
0x1800228a3  retn
0x1800228a4  mov     rcx, [rsi+80h]; bstrString
0x1800228ab  call    cs:__imp_SysFreeString
0x1800228b1  mov     [rsi+80h], rbx
0x1800228b8  mov     rcx, [rsi+78h]; bstrString
0x1800228bc  call    cs:__imp_SysFreeString
0x1800228c2  mov     qword ptr [rsi+78h], 0
0x1800228ca  mov     rcx, [rsi+88h]; bstrString
0x1800228d1  call    cs:__imp_SysFreeString
0x1800228d7  mov     rax, [rsp+48h+bstrString]
0x1800228dc  mov     [rsi+88h], rax
0x1800228e3  xor     edi, edi
0x1800228e5  mov     rax, [rsi]
0x1800228e8  mov     rcx, rsi
0x1800228eb  mov     rax, [rax+40h]
0x1800228ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228f4  xor     ebx, ebx
0x1800228f6  jmp     loc_18002286F
```
