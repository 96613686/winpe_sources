# FwOpenPort::put_Enabled(short)

- ea: `0x18003c570`
- end: `0x18003c72b`
- name: `?put_Enabled@FwOpenPort@@UEAAJF@Z`
- size: `443`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x18003bd9c`
- `0x18003c570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c5b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c5b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c6d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c6d9`
- `fwbase!FwReportReturnError` at `0x18003c6c9`
- `fwbase!FwReportReturnError` at `0x18003c6f2`
- `fwbase!FwReportReturnError` at `0x18003c6c9`
- `fwbase!FwReportReturnError` at `0x18003c6f2`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c5d0`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c5d0`

## string_xrefs

- `0x18003c6c2`: `FwOpenPort::put_Enabled`
- `0x18003c6eb`: `FwOpenPort::put_Enabled`

## pseudocode

```c
__int64 __fastcall FwOpenPort::put_Enabled(FwOpenPort *this, __int16 a2)
{
  struct _tag_FW_RULE **v4; // rsi
  int DefaultOpenPortRule; // eax
  int v6; // ebx
  struct _tag_FW_RULE *v7; // rax
  _OWORD *v8; // rcx
  __int64 v9; // rdx
  __int128 v10; // xmm1
  _BYTE v12[288]; // [rsp+20h] [rbp-228h] BYREF
  int v13; // [rsp+140h] [rbp-108h]
  __int16 v14; // [rsp+144h] [rbp-104h]

  memset_0(v12, 0, 0x1F8u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v4 = (struct _tag_FW_RULE **)((char *)this + 72);
  if ( !*((_QWORD *)this + 9) )
  {
    DefaultOpenPortRule = CreateDefaultOpenPortRule((char *)this + 72, *((unsigned int *)this + 16));
    v6 = DefaultOpenPortRule;
    if ( DefaultOpenPortRule < 0 )
      goto LABEL_9;
  }
  v7 = *v4;
  v8 = v12;
  v9 = 3;
  do
  {
    *v8 = *(_OWORD *)v7;
    v8[1] = *((_OWORD *)v7 + 1);
    v8[2] = *((_OWORD *)v7 + 2);
    v8[3] = *((_OWORD *)v7 + 3);
    v8[4] = *((_OWORD *)v7 + 4);
    v8[5] = *((_OWORD *)v7 + 5);
    v8[6] = *((_OWORD *)v7 + 6);
    v10 = *((_OWORD *)v7 + 7);
    v7 = (struct _tag_FW_RULE *)((char *)v7 + 128);
    v8[7] = v10;
    v8 += 8;
    --v9;
  }
  while ( v9 );
  *v8 = *(_OWORD *)v7;
  v8[1] = *((_OWORD *)v7 + 1);
  v8[2] = *((_OWORD *)v7 + 2);
  v8[3] = *((_OWORD *)v7 + 3);
  v8[4] = *((_OWORD *)v7 + 4);
  v8[5] = *((_OWORD *)v7 + 5);
  v8[6] = *((_OWORD *)v7 + 6);
  *((_QWORD *)v8 + 14) = *((_QWORD *)v7 + 14);
  if ( a2 == -1 )
  {
    v14 |= 1u;
    v13 = 3;
  }
  else
  {
    v14 &= ~1u;
  }
  DefaultOpenPortRule = FwOpenPort::SetRule(this, (const struct _tag_FW_RULE *)v12, *v4);
  v6 = DefaultOpenPortRule;
  if ( DefaultOpenPortRule < 0 )
LABEL_9:
    FwReportReturnError("FwOpenPort::put_Enabled", (unsigned int)DefaultOpenPortRule);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::put_Enabled", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003c570  mov     [rsp+arg_8], rbx
0x18003c575  mov     [rsp+arg_10], rbp
0x18003c57a  push    rsi
0x18003c57b  push    rdi
0x18003c57c  push    r14
0x18003c57e  sub     rsp, 230h
0x18003c585  mov     rax, cs:__security_cookie
0x18003c58c  xor     rax, rsp
0x18003c58f  mov     [rsp+248h+var_28], rax
0x18003c597  movzx   r14d, dx
0x18003c59b  mov     rdi, rcx
0x18003c59e  xor     edx, edx; Val
0x18003c5a0  lea     rcx, [rsp+248h+var_228]; void *
0x18003c5a5  mov     r8d, 1F8h; Size
0x18003c5ab  call    memset_0
0x18003c5b0  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003c5b4  call    cs:__imp_EnterCriticalSection
0x18003c5bb  nop     dword ptr [rax+rax+00h]
0x18003c5c0  lea     rsi, [rdi+48h]
0x18003c5c4  cmp     qword ptr [rsi], 0
0x18003c5c8  jnz     short loc_18003C5E6
0x18003c5ca  mov     edx, [rdi+40h]
0x18003c5cd  mov     rcx, rsi
0x18003c5d0  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003c5d7  nop     dword ptr [rax+rax+00h]
0x18003c5dc  mov     ebx, eax
0x18003c5de  test    eax, eax
0x18003c5e0  js      loc_18003C6C0
0x18003c5e6  mov     rax, [rsi]
0x18003c5e9  lea     rcx, [rsp+248h+var_228]
0x18003c5ee  mov     r8d, 3
0x18003c5f4  mov     edx, r8d
0x18003c5f7  lea     r9d, [r8+7Dh]
0x18003c5fb  movups  xmm0, xmmword ptr [rax]
0x18003c5fe  movups  xmmword ptr [rcx], xmm0
0x18003c601  movups  xmm1, xmmword ptr [rax+10h]
0x18003c605  movups  xmmword ptr [rcx+10h], xmm1
0x18003c609  movups  xmm0, xmmword ptr [rax+20h]
0x18003c60d  movups  xmmword ptr [rcx+20h], xmm0
0x18003c611  movups  xmm1, xmmword ptr [rax+30h]
0x18003c615  movups  xmmword ptr [rcx+30h], xmm1
0x18003c619  movups  xmm0, xmmword ptr [rax+40h]
0x18003c61d  movups  xmmword ptr [rcx+40h], xmm0
0x18003c621  movups  xmm1, xmmword ptr [rax+50h]
0x18003c625  movups  xmmword ptr [rcx+50h], xmm1
0x18003c629  movups  xmm0, xmmword ptr [rax+60h]
0x18003c62d  movups  xmmword ptr [rcx+60h], xmm0
0x18003c631  movups  xmm1, xmmword ptr [rax+70h]
0x18003c635  add     rax, r9
0x18003c638  movups  xmmword ptr [rcx+70h], xmm1
0x18003c63c  add     rcx, r9
0x18003c63f  sub     rdx, 1
0x18003c643  jnz     short loc_18003C5FB
0x18003c645  movups  xmm0, xmmword ptr [rax]
0x18003c648  movups  xmmword ptr [rcx], xmm0
0x18003c64b  movups  xmm1, xmmword ptr [rax+10h]
0x18003c64f  movups  xmmword ptr [rcx+10h], xmm1
0x18003c653  movups  xmm0, xmmword ptr [rax+20h]
0x18003c657  movups  xmmword ptr [rcx+20h], xmm0
0x18003c65b  movups  xmm1, xmmword ptr [rax+30h]
0x18003c65f  movups  xmmword ptr [rcx+30h], xmm1
0x18003c663  movups  xmm0, xmmword ptr [rax+40h]
0x18003c667  movups  xmmword ptr [rcx+40h], xmm0
0x18003c66b  movups  xmm1, xmmword ptr [rax+50h]
0x18003c66f  movups  xmmword ptr [rcx+50h], xmm1
0x18003c673  movups  xmm0, xmmword ptr [rax+60h]
0x18003c677  movups  xmmword ptr [rcx+60h], xmm0
0x18003c67b  mov     rax, [rax+70h]
0x18003c67f  mov     [rcx+70h], rax
0x18003c683  cmp     r14w, 0FFFFh
0x18003c688  jnz     short loc_18003C69D
0x18003c68a  or      [rsp+248h+var_104], 1
0x18003c693  mov     [rsp+248h+var_108], r8d
0x18003c69b  jmp     short loc_18003C6AA
0x18003c69d  mov     eax, 0FFFEh
0x18003c6a2  and     [rsp+248h+var_104], ax
0x18003c6aa  mov     r8, [rsi]; struct _tag_FW_RULE *
0x18003c6ad  lea     rdx, [rsp+248h+var_228]; struct _tag_FW_RULE *
0x18003c6b2  mov     rcx, rdi; this
0x18003c6b5  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x18003c6ba  mov     ebx, eax
0x18003c6bc  test    eax, eax
0x18003c6be  jns     short loc_18003C6D5
0x18003c6c0  mov     edx, eax
0x18003c6c2  lea     rcx, aFwopenportPutE; "FwOpenPort::put_Enabled"
0x18003c6c9  call    cs:__imp_FwReportReturnError
0x18003c6d0  nop     dword ptr [rax+rax+00h]
0x18003c6d5  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003c6d9  call    cs:__imp_LeaveCriticalSection
0x18003c6e0  nop     dword ptr [rax+rax+00h]
0x18003c6e5  test    ebx, ebx
0x18003c6e7  jns     short loc_18003C700
0x18003c6e9  mov     edx, ebx
0x18003c6eb  lea     rcx, aFwopenportPutE; "FwOpenPort::put_Enabled"
0x18003c6f2  call    cs:__imp_FwReportReturnError
0x18003c6f9  nop     dword ptr [rax+rax+00h]
0x18003c6fe  mov     ebx, eax
0x18003c700  mov     eax, ebx
0x18003c702  mov     rcx, [rsp+248h+var_28]
0x18003c70a  xor     rcx, rsp; StackCookie
0x18003c70d  call    __security_check_cookie
0x18003c712  lea     r11, [rsp+248h+var_18]
0x18003c71a  mov     rbx, [r11+28h]
0x18003c71e  mov     rbp, [r11+30h]
0x18003c722  mov     rsp, r11
0x18003c725  pop     r14
0x18003c727  pop     rdi
0x18003c728  pop     rsi
0x18003c729  retn
```
