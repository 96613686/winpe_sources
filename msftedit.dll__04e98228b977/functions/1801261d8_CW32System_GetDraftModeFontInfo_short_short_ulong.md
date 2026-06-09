# CW32System::GetDraftModeFontInfo(short &,short &,ulong &)

- ea: `0x1801261d8`
- end: `0x1801262ff`
- name: `?GetDraftModeFontInfo@CW32System@@SA_NAEAF0AEAK@Z`
- size: `295`
- prototype: `bool __fastcall(__int16 *, __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180027500`
- `0x1800448b4`
- `0x1800b5cc4`

## callees

- `0x180056d48`
- `0x1801261d8`
- `0x18012c7a0`
- `0x18013ce80`
- `0x18013dce6`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180126244`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180126244`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x1801262a5`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x1801262a5`

## pseudocode

```c
bool __fastcall CW32System::GetDraftModeFontInfo(__int16 *a1, __int16 *a2, unsigned int *a3)
{
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rcx
  bool result; // al
  int pvParam; // [rsp+20h] [rbp-228h] BYREF
  _BYTE v13[404]; // [rsp+24h] [rbp-224h] BYREF
  int v14; // [rsp+1B8h] [rbp-90h]
  unsigned __int16 Src[38]; // [rsp+1D4h] [rbp-74h] BYREF

  if ( !CW32System::_draftModeFontInfo && !word_1802E41CA )
  {
    memset_0(v13, 0, 0x1F4u);
    pvParam = 504;
    if ( SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0) )
    {
      word_1802E41CA = CFICache::GetFontNameIndex(Src, 1);
      v8 = (unsigned int)((1440 * v14) >> 31);
      v9 = 1440 * v14 / CW32System::_yPerInchScreenDC;
      v10 = (unsigned int)(v9 + 0x8000);
      if ( (unsigned int)v10 > 0xFFFF )
      {
        LODWORD(v8) = 1440 * v14 % CW32System::_yPerInchScreenDC;
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v10, v8, v6, v7);
      }
      word_1802E41CC = 1440 * v14 / CW32System::_yPerInchScreenDC;
      if ( (__int16)v9 <= 0 )
        word_1802E41CC = -(__int16)v9;
    }
    dword_1802E41D0 = GetSysColor(8);
  }
  result = 1;
  *a1 = word_1802E41CA;
  *a2 = word_1802E41CC;
  *a3 = dword_1802E41D0;
  return result;
}

```

## disassembly

```asm
0x1801261d8  mov     [rsp+arg_18], rbx
0x1801261dd  push    rbp
0x1801261de  push    rsi
0x1801261df  push    rdi
0x1801261e0  sub     rsp, 230h
0x1801261e7  mov     rax, cs:__security_cookie
0x1801261ee  xor     rax, rsp
0x1801261f1  mov     [rsp+248h+var_28], rax
0x1801261f9  xor     ebp, ebp
0x1801261fb  mov     rsi, r8
0x1801261fe  cmp     cs:?_draftModeFontInfo@CW32System@@0UDraftModeFontInfo@1@A, bpl; CW32System::DraftModeFontInfo CW32System::_draftModeFontInfo
0x180126205  mov     rdi, rdx
0x180126208  mov     rbx, rcx
0x18012620b  jnz     loc_1801262B7
0x180126211  cmp     cs:word_1802E41CA, bp
0x180126218  jnz     loc_1801262B7
0x18012621e  xor     edx, edx; Val
0x180126220  lea     rcx, [rsp+248h+var_224]; void *
0x180126225  mov     r8d, 1F4h; Size
0x18012622b  call    memset_0
0x180126230  mov     edx, 1F8h; uiParam
0x180126235  lea     r8, [rsp+248h+pvParam]; pvParam
0x18012623a  xor     r9d, r9d; fWinIni
0x18012623d  mov     [rsp+248h+pvParam], edx
0x180126241  lea     ecx, [rbp+29h]; uiAction
0x180126244  call    cs:__imp_SystemParametersInfoW
0x18012624b  nop     dword ptr [rax+rax+00h]
0x180126250  test    eax, eax
0x180126252  jz      short loc_1801262A0
0x180126254  mov     dl, 1; bool
0x180126256  lea     rcx, [rsp+248h+Src]; Src
0x18012625e  call    ?GetFontNameIndex@CFICache@@SAFPEBG_N@Z; CFICache::GetFontNameIndex(ushort const *,bool)
0x180126263  mov     cs:word_1802E41CA, ax
0x18012626a  imul    eax, [rsp+248h+var_90], 5A0h
0x180126275  cdq
0x180126276  idiv    cs:?_yPerInchScreenDC@CW32System@@0JA; long CW32System::_yPerInchScreenDC
0x18012627c  lea     ecx, [rax+8000h]
0x180126282  cmp     ecx, 0FFFFh
0x180126288  ja      short loc_1801262F9
0x18012628a  mov     cs:word_1802E41CC, ax
0x180126291  test    ax, ax
0x180126294  jg      short loc_1801262A0
0x180126296  neg     ax
0x180126299  mov     cs:word_1802E41CC, ax
0x1801262a0  mov     ecx, 8; nIndex
0x1801262a5  call    cs:__imp_GetSysColor
0x1801262ac  nop     dword ptr [rax+rax+00h]
0x1801262b1  mov     cs:dword_1802E41D0, eax
0x1801262b7  movzx   ecx, cs:word_1802E41CA
0x1801262be  mov     al, 1
0x1801262c0  mov     [rbx], cx
0x1801262c3  movzx   ecx, cs:word_1802E41CC
0x1801262ca  mov     [rdi], cx
0x1801262cd  mov     ecx, cs:dword_1802E41D0
0x1801262d3  mov     [rsi], ecx
0x1801262d5  mov     rcx, [rsp+248h+var_28]
0x1801262dd  xor     rcx, rsp; StackCookie
0x1801262e0  call    __security_check_cookie
0x1801262e5  mov     rbx, [rsp+248h+arg_18]
0x1801262ed  add     rsp, 230h
0x1801262f4  pop     rdi
0x1801262f5  pop     rsi
0x1801262f6  pop     rbp
0x1801262f7  retn
0x1801262f9  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
