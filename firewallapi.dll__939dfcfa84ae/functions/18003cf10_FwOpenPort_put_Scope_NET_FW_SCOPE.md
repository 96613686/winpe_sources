# FwOpenPort::put_Scope(NET_FW_SCOPE_)

- ea: `0x18003cf10`
- end: `0x18003d105`
- name: `?put_Scope@FwOpenPort@@UEAAJW4NET_FW_SCOPE_@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, enum NET_FW_SCOPE_)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x18003bd9c`
- `0x18003cf10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cf69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cf69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d0b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d0b4`
- `fwbase!FwReportReturnError` at `0x18003d0a4`
- `fwbase!FwReportReturnError` at `0x18003d0cd`
- `fwbase!FwReportReturnError` at `0x18003d0a4`
- `fwbase!FwReportReturnError` at `0x18003d0cd`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003cfa7`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003cfa7`

## string_xrefs

- `0x18003d09d`: `FwOpenPort::put_Scope`
- `0x18003d0c6`: `FwOpenPort::put_Scope`

## pseudocode

```c
__int64 __fastcall FwOpenPort::put_Scope(FwOpenPort *this, enum NET_FW_SCOPE_ a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  struct _tag_FW_RULE **v6; // rdi
  int DefaultOpenPortRule; // eax
  struct _tag_FW_RULE *v8; // rax
  _OWORD *v9; // rdx
  __int64 v10; // rcx
  __int128 v11; // xmm1
  struct _tag_FW_RULE *v12; // r8
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  _OWORD v16[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h]
  _BYTE v18[176]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v19; // [rsp+120h] [rbp+20h]
  __int128 v20; // [rsp+130h] [rbp+30h]
  __int128 v21; // [rsp+140h] [rbp+40h]
  __int128 v22; // [rsp+150h] [rbp+50h]
  __int64 v23; // [rsp+160h] [rbp+60h]

  memset_0(v16, 0, 0x48u);
  memset_0(v18, 0, 0x1F8u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
  {
    if ( a2 != NET_FW_SCOPE_LOCAL_SUBNET )
    {
      v4 = -2147024809;
      v5 = 2147942487LL;
      goto LABEL_11;
    }
    *(_QWORD *)&v16[0] = 0x100000001LL;
  }
  v6 = (struct _tag_FW_RULE **)((char *)this + 72);
  if ( *((_QWORD *)this + 9)
    || (DefaultOpenPortRule = CreateDefaultOpenPortRule((char *)this + 72, *((unsigned int *)this + 16)),
        v4 = DefaultOpenPortRule,
        DefaultOpenPortRule >= 0) )
  {
    v8 = *v6;
    v9 = v18;
    v10 = 3;
    do
    {
      *v9 = *(_OWORD *)v8;
      v9[1] = *((_OWORD *)v8 + 1);
      v9[2] = *((_OWORD *)v8 + 2);
      v9[3] = *((_OWORD *)v8 + 3);
      v9[4] = *((_OWORD *)v8 + 4);
      v9[5] = *((_OWORD *)v8 + 5);
      v9[6] = *((_OWORD *)v8 + 6);
      v11 = *((_OWORD *)v8 + 7);
      v8 = (struct _tag_FW_RULE *)((char *)v8 + 128);
      v9[7] = v11;
      v9 += 8;
      --v10;
    }
    while ( v10 );
    v12 = *v6;
    *v9 = *(_OWORD *)v8;
    v9[1] = *((_OWORD *)v8 + 1);
    v9[2] = *((_OWORD *)v8 + 2);
    v9[3] = *((_OWORD *)v8 + 3);
    v9[4] = *((_OWORD *)v8 + 4);
    v9[5] = *((_OWORD *)v8 + 5);
    v13 = v16[1];
    v9[6] = *((_OWORD *)v8 + 6);
    v14 = v16[0];
    *((_QWORD *)v9 + 14) = *((_QWORD *)v8 + 14);
    v19 = v14;
    v21 = v16[2];
    v20 = v13;
    v23 = v17;
    v22 = v16[3];
    DefaultOpenPortRule = FwOpenPort::SetRule(this, (const struct _tag_FW_RULE *)v18, v12);
    v4 = DefaultOpenPortRule;
    if ( DefaultOpenPortRule >= 0 )
      goto LABEL_12;
  }
  v5 = (unsigned int)DefaultOpenPortRule;
LABEL_11:
  FwReportReturnError("FwOpenPort::put_Scope", v5);
LABEL_12:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::put_Scope", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003cf10  mov     [rsp-8+arg_8], rbx
0x18003cf15  mov     [rsp-8+arg_10], rsi
0x18003cf1a  push    rbp
0x18003cf1b  push    rdi
0x18003cf1c  push    r14
0x18003cf1e  lea     rbp, [rsp-180h]
0x18003cf26  sub     rsp, 280h
0x18003cf2d  mov     rax, cs:__security_cookie
0x18003cf34  xor     rax, rsp
0x18003cf37  mov     [rbp+190h+var_20], rax
0x18003cf3e  mov     ebx, edx
0x18003cf40  mov     rsi, rcx
0x18003cf43  xor     edx, edx; Val
0x18003cf45  lea     rcx, [rsp+290h+var_270]; void *
0x18003cf4a  lea     r8d, [rdx+48h]; Size
0x18003cf4e  call    memset_0
0x18003cf53  xor     edx, edx; Val
0x18003cf55  lea     rcx, [rsp+290h+var_220]; void *
0x18003cf5a  mov     r8d, 1F8h; Size
0x18003cf60  call    memset_0
0x18003cf65  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003cf69  call    cs:__imp_EnterCriticalSection
0x18003cf70  nop     dword ptr [rax+rax+00h]
0x18003cf75  test    ebx, ebx
0x18003cf77  jz      short loc_18003CF97
0x18003cf79  cmp     ebx, 1
0x18003cf7c  jz      short loc_18003CF8A
0x18003cf7e  mov     ebx, 80070057h
0x18003cf83  mov     edx, ebx
0x18003cf85  jmp     loc_18003D09D
0x18003cf8a  mov     eax, 1
0x18003cf8f  mov     dword ptr [rsp+290h+var_270+4], eax
0x18003cf93  mov     dword ptr [rsp+290h+var_270], eax
0x18003cf97  lea     rdi, [rsi+48h]
0x18003cf9b  cmp     qword ptr [rdi], 0
0x18003cf9f  jnz     short loc_18003CFBD
0x18003cfa1  mov     edx, [rsi+40h]
0x18003cfa4  mov     rcx, rdi
0x18003cfa7  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003cfae  nop     dword ptr [rax+rax+00h]
0x18003cfb3  mov     ebx, eax
0x18003cfb5  test    eax, eax
0x18003cfb7  js      loc_18003D09B
0x18003cfbd  mov     rax, [rdi]
0x18003cfc0  lea     rdx, [rsp+290h+var_220]
0x18003cfc5  mov     ecx, 3
0x18003cfca  lea     r8d, [rcx+7Dh]
0x18003cfce  movups  xmm0, xmmword ptr [rax]
0x18003cfd1  movups  xmmword ptr [rdx], xmm0
0x18003cfd4  movups  xmm1, xmmword ptr [rax+10h]
0x18003cfd8  movups  xmmword ptr [rdx+10h], xmm1
0x18003cfdc  movups  xmm0, xmmword ptr [rax+20h]
0x18003cfe0  movups  xmmword ptr [rdx+20h], xmm0
0x18003cfe4  movups  xmm1, xmmword ptr [rax+30h]
0x18003cfe8  movups  xmmword ptr [rdx+30h], xmm1
0x18003cfec  movups  xmm0, xmmword ptr [rax+40h]
0x18003cff0  movups  xmmword ptr [rdx+40h], xmm0
0x18003cff4  movups  xmm1, xmmword ptr [rax+50h]
0x18003cff8  movups  xmmword ptr [rdx+50h], xmm1
0x18003cffc  movups  xmm0, xmmword ptr [rax+60h]
0x18003d000  movups  xmmword ptr [rdx+60h], xmm0
0x18003d004  movups  xmm1, xmmword ptr [rax+70h]
0x18003d008  add     rax, r8
0x18003d00b  movups  xmmword ptr [rdx+70h], xmm1
0x18003d00f  add     rdx, r8
0x18003d012  sub     rcx, 1
0x18003d016  jnz     short loc_18003CFCE
0x18003d018  movups  xmm0, xmmword ptr [rax]
0x18003d01b  mov     r8, [rdi]; struct _tag_FW_RULE *
0x18003d01e  mov     rcx, rsi; this
0x18003d021  movups  xmmword ptr [rdx], xmm0
0x18003d024  movups  xmm1, xmmword ptr [rax+10h]
0x18003d028  movups  xmmword ptr [rdx+10h], xmm1
0x18003d02c  movups  xmm0, xmmword ptr [rax+20h]
0x18003d030  movups  xmmword ptr [rdx+20h], xmm0
0x18003d034  movups  xmm1, xmmword ptr [rax+30h]
0x18003d038  movups  xmmword ptr [rdx+30h], xmm1
0x18003d03c  movups  xmm0, xmmword ptr [rax+40h]
0x18003d040  movups  xmmword ptr [rdx+40h], xmm0
0x18003d044  movups  xmm1, xmmword ptr [rax+50h]
0x18003d048  movups  xmmword ptr [rdx+50h], xmm1
0x18003d04c  movups  xmm0, xmmword ptr [rax+60h]
0x18003d050  movaps  xmm1, [rsp+290h+var_260]
0x18003d055  movups  xmmword ptr [rdx+60h], xmm0
0x18003d059  mov     rax, [rax+70h]
0x18003d05d  movaps  xmm0, [rsp+290h+var_270]
0x18003d062  mov     [rdx+70h], rax
0x18003d066  lea     rdx, [rsp+290h+var_220]; struct _tag_FW_RULE *
0x18003d06b  movaps  [rbp+190h+var_170], xmm0
0x18003d06f  movaps  xmm0, [rsp+290h+var_250]
0x18003d074  movaps  [rbp+190h+var_150], xmm0
0x18003d078  movsd   xmm0, [rsp+290h+var_230]
0x18003d07e  movaps  [rbp+190h+var_160], xmm1
0x18003d082  movaps  xmm1, [rsp+290h+var_240]
0x18003d087  movsd   [rbp+190h+var_130], xmm0
0x18003d08c  movaps  [rbp+190h+var_140], xmm1
0x18003d090  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x18003d095  mov     ebx, eax
0x18003d097  test    eax, eax
0x18003d099  jns     short loc_18003D0B0
0x18003d09b  mov     edx, eax
0x18003d09d  lea     rcx, aFwopenportPutS; "FwOpenPort::put_Scope"
0x18003d0a4  call    cs:__imp_FwReportReturnError
0x18003d0ab  nop     dword ptr [rax+rax+00h]
0x18003d0b0  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003d0b4  call    cs:__imp_LeaveCriticalSection
0x18003d0bb  nop     dword ptr [rax+rax+00h]
0x18003d0c0  test    ebx, ebx
0x18003d0c2  jns     short loc_18003D0DB
0x18003d0c4  mov     edx, ebx
0x18003d0c6  lea     rcx, aFwopenportPutS; "FwOpenPort::put_Scope"
0x18003d0cd  call    cs:__imp_FwReportReturnError
0x18003d0d4  nop     dword ptr [rax+rax+00h]
0x18003d0d9  mov     ebx, eax
0x18003d0db  mov     eax, ebx
0x18003d0dd  mov     rcx, [rbp+190h+var_20]
0x18003d0e4  xor     rcx, rsp; StackCookie
0x18003d0e7  call    __security_check_cookie
0x18003d0ec  lea     r11, [rsp+290h+var_10]
0x18003d0f4  mov     rbx, [r11+28h]
0x18003d0f8  mov     rsi, [r11+30h]
0x18003d0fc  mov     rsp, r11
0x18003d0ff  pop     r14
0x18003d101  pop     rdi
0x18003d102  pop     rbp
0x18003d103  retn
```
