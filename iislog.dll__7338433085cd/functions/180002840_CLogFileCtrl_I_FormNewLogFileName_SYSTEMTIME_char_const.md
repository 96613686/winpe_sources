# CLogFileCtrl::I_FormNewLogFileName(_SYSTEMTIME *,char const *)

- ea: `0x180002840`
- end: `0x180002a18`
- name: `?I_FormNewLogFileName@CLogFileCtrl@@IEAAXPEAU_SYSTEMTIME@@PEBD@Z`
- size: `472`
- prototype: `void __fastcall(CLogFileCtrl *__hidden this, struct _SYSTEMTIME *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004140`
- `0x1800078b0`
- `0x18000c150`

## callees

- `0x180002840`
- `0x18000eca0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x1800028e5`
- `msvcrt!sprintf_s` at `0x18000291e`
- `msvcrt!sprintf_s` at `0x1800029b8`
- `msvcrt!sprintf_s` at `0x1800029e4`
- `msvcrt!sprintf_s` at `0x1800028e5`
- `msvcrt!sprintf_s` at `0x18000291e`
- `msvcrt!sprintf_s` at `0x1800029b8`
- `msvcrt!sprintf_s` at `0x1800029e4`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x1800029f9`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x1800029f9`

## pseudocode

```c
void __fastcall CLogFileCtrl::I_FormNewLogFileName(CLogFileCtrl *this, struct _SYSTEMTIME *a2, const char *a3)
{
  int v4; // ecx
  unsigned __int16 v5; // r11
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  char Buffer[272]; // [rsp+50h] [rbp-128h] BYREF

  v4 = *((_DWORD *)this + 27);
  v5 = a2->wYear % 0x64u;
  if ( !v4 )
    goto LABEL_11;
  v6 = v4 - 1;
  if ( !v6 )
  {
    sprintf_s(Buffer, 0x105u, "%.2s%02.2u%02u%02u.%s", a3, v5, a2->wMonth, a2->wDay, "log");
    goto LABEL_12;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    sprintf_s(
      Buffer,
      0x105u,
      "%.2s%02.2u%02u%02u.%s",
      a3,
      v5,
      a2->wMonth,
      ((unsigned int)a2->wDay - 1) / 7 + 1 + (a2->wDayOfWeek < ((unsigned int)a2->wDay - 1) % 7),
      "log");
    goto LABEL_12;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    sprintf_s(Buffer, 0x105u, "%.2s%02u%02u.%s", a3, v5, a2->wMonth, "log");
    goto LABEL_12;
  }
  if ( v8 != 1 )
  {
LABEL_11:
    sprintf_s(Buffer, 0x105u, "%.6s%u.%s", a3, *((_DWORD *)this + 18), "log");
    ++*((_DWORD *)this + 18);
    goto LABEL_12;
  }
  sprintf_s(Buffer, 0x105u, "%.2s%02.2u%02u%02u%02u.%s", a3, v5, a2->wMonth, a2->wDay, a2->wHour, "log");
LABEL_12:
  STR::Copy((CLogFileCtrl *)((char *)this + 296), Buffer);
}

```

## disassembly

```asm
0x180002840  push    rbx
0x180002842  sub     rsp, 170h
0x180002849  mov     rax, cs:__security_cookie
0x180002850  xor     rax, rsp
0x180002853  mov     [rsp+178h+var_18], rax
0x18000285b  movzx   r11d, word ptr [rdx]
0x18000285f  mov     r10, rdx
0x180002862  mov     eax, 51EB851Fh
0x180002867  mov     rbx, rcx
0x18000286a  mov     ecx, [rcx+6Ch]
0x18000286d  mov     r9, r8
0x180002870  mul     r11d
0x180002873  shr     edx, 5
0x180002876  imul    eax, edx, 64h ; 'd'
0x180002879  sub     r11d, eax
0x18000287c  test    ecx, ecx
0x18000287e  jz      loc_1800029C0
0x180002884  sub     ecx, 1
0x180002887  jz      loc_180002981
0x18000288d  sub     ecx, 1
0x180002890  jz      loc_180002929
0x180002896  sub     ecx, 1
0x180002899  jz      short loc_1800028F0
0x18000289b  cmp     ecx, 1
0x18000289e  jnz     loc_1800029C0
0x1800028a4  movzx   ecx, word ptr [r10+6]
0x1800028a9  movzx   edx, word ptr [r10+2]
0x1800028ae  movzx   eax, word ptr [r10+8]
0x1800028b3  lea     r10, aLog; "log"
0x1800028ba  mov     [rsp+178h+var_138], r10
0x1800028bf  mov     dword ptr [rsp+178h+var_140], eax
0x1800028c3  mov     dword ptr [rsp+178h+var_148], ecx
0x1800028c7  lea     rcx, [rsp+178h+Buffer]; Buffer
0x1800028cc  movzx   r8d, r11w
0x1800028d0  mov     dword ptr [rsp+178h+var_150], edx
0x1800028d4  mov     edx, 105h; BufferCount
0x1800028d9  mov     [rsp+178h+var_158], r8d
0x1800028de  lea     r8, Format; "%.2s%02.2u%02u%02u%02u.%s"
0x1800028e5  call    cs:__imp_sprintf_s
0x1800028eb  jmp     loc_1800029ED
0x1800028f0  movzx   eax, word ptr [r10+2]
0x1800028f5  lea     r8, a2s02u02uS; "%.2s%02u%02u.%s"
0x1800028fc  movzx   ecx, r11w
0x180002900  lea     r10, aLog; "log"
0x180002907  mov     [rsp+178h+var_148], r10
0x18000290c  mov     edx, 105h; BufferCount
0x180002911  mov     dword ptr [rsp+178h+var_150], eax
0x180002915  mov     [rsp+178h+var_158], ecx
0x180002919  lea     rcx, [rsp+178h+Buffer]; Buffer
0x18000291e  call    cs:__imp_sprintf_s
0x180002924  jmp     loc_1800029ED
0x180002929  movzx   ecx, word ptr [r10+6]
0x18000292e  mov     eax, 24924925h
0x180002933  dec     ecx
0x180002935  mul     ecx
0x180002937  mov     r8d, ecx
0x18000293a  sub     r8d, edx
0x18000293d  shr     r8d, 1
0x180002940  add     r8d, edx
0x180002943  shr     r8d, 2
0x180002947  imul    eax, r8d, 7
0x18000294b  sub     ecx, eax
0x18000294d  movzx   eax, word ptr [r10+4]
0x180002952  cmp     eax, ecx
0x180002954  movzx   eax, word ptr [r10+2]
0x180002959  lea     r10, aLog; "log"
0x180002960  movzx   ecx, r11w
0x180002964  sbb     edx, edx
0x180002966  mov     [rsp+178h+var_140], r10
0x18000296b  neg     edx
0x18000296d  inc     r8d
0x180002970  add     edx, r8d
0x180002973  mov     dword ptr [rsp+178h+var_148], edx
0x180002977  mov     dword ptr [rsp+178h+var_150], eax
0x18000297b  mov     [rsp+178h+var_158], ecx
0x18000297f  jmp     short loc_1800029A7
0x180002981  movzx   eax, word ptr [r10+6]
0x180002986  movzx   ecx, word ptr [r10+2]
0x18000298b  lea     r10, aLog; "log"
0x180002992  mov     [rsp+178h+var_140], r10
0x180002997  mov     dword ptr [rsp+178h+var_148], eax
0x18000299b  movzx   edx, r11w
0x18000299f  mov     dword ptr [rsp+178h+var_150], ecx
0x1800029a3  mov     [rsp+178h+var_158], edx
0x1800029a7  lea     r8, a2s022u02u02uS; "%.2s%02.2u%02u%02u.%s"
0x1800029ae  mov     edx, 105h; BufferCount
0x1800029b3  lea     rcx, [rsp+178h+Buffer]; Buffer
0x1800029b8  call    cs:__imp_sprintf_s
0x1800029be  jmp     short loc_1800029ED
0x1800029c0  mov     eax, [rbx+48h]
0x1800029c3  lea     r10, aLog; "log"
0x1800029ca  mov     [rsp+178h+var_150], r10
0x1800029cf  lea     r8, a6sUS; "%.6s%u.%s"
0x1800029d6  mov     edx, 105h; BufferCount
0x1800029db  mov     [rsp+178h+var_158], eax
0x1800029df  lea     rcx, [rsp+178h+Buffer]; Buffer
0x1800029e4  call    cs:__imp_sprintf_s
0x1800029ea  inc     dword ptr [rbx+48h]
0x1800029ed  lea     rcx, [rbx+128h]
0x1800029f4  lea     rdx, [rsp+178h+Buffer]
0x1800029f9  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x1800029ff  mov     rcx, [rsp+178h+var_18]
0x180002a07  xor     rcx, rsp; StackCookie
0x180002a0a  call    __security_check_cookie
0x180002a0f  add     rsp, 170h
0x180002a16  pop     rbx
0x180002a17  retn
```
