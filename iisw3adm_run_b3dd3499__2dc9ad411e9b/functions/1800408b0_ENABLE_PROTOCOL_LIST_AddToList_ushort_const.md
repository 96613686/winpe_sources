# ENABLE_PROTOCOL_LIST::AddToList(ushort const *)

- ea: `0x1800408b0`
- end: `0x180040a52`
- name: `?AddToList@ENABLE_PROTOCOL_LIST@@QEAAJPEBG@Z`
- size: `418`
- prototype: `__int64 __fastcall(ENABLE_PROTOCOL_LIST *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180015850`
- `0x180016174`
- `0x180040aac`

## callees

- `0x18004082c`
- `0x1800408b0`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `msvcrt!wcschr` at `0x180040980`
- `msvcrt!wcschr` at `0x1800409a4`
- `msvcrt!wcschr` at `0x180040980`
- `msvcrt!wcschr` at `0x1800409a4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180040a1e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180040a1e`
- `iisutil!PuDbgPrintError` at `0x180040958`
- `iisutil!PuDbgPrintError` at `0x180040958`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180040911`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180040911`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180040903`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180040903`

## string_xrefs

- `0x180040934`: `Failed to make a copy of the enabled protocols to work with \n`
- `0x180040940`: `ENABLE_PROTOCOL_LIST::AddToList`
- `0x180040951`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\enable_protocol_list.cxx`

## pseudocode

```c
__int64 __fastcall ENABLE_PROTOCOL_LIST::AddToList(ENABLE_PROTOCOL_LIST *this, const unsigned __int16 *a2)
{
  int v4; // esi
  wchar_t *v5; // rdi
  __int16 v6; // bp
  const wchar_t *v7; // rcx
  wchar_t *v8; // rbx
  wchar_t v9; // dx
  wchar_t *v10; // rcx
  const unsigned __int16 *i; // rdx
  __int64 v12; // rax
  wchar_t *j; // rax
  wchar_t *v14; // rax
  _BYTE v16[32]; // [rsp+30h] [rbp-278h] BYREF
  wchar_t *Str; // [rsp+50h] [rbp-258h]
  unsigned __int16 v18[256]; // [rsp+70h] [rbp-238h] BYREF

  memset_0(v18, 0, sizeof(v18));
  STRU::STRU((STRU *)v16, v18, 0x100u);
  v4 = STRU::Copy((STRU *)v16, a2);
  if ( v4 >= 0 )
  {
    v5 = Str;
    v6 = 32;
    while ( 1 )
    {
      v7 = v5;
      if ( v6 != 32 )
        break;
      v8 = wcschr(v5, 0x3Au);
      if ( !v8 )
      {
        v6 = 44;
        v7 = v5;
        v9 = 44;
LABEL_10:
        v8 = wcschr(v7, v9);
        goto LABEL_11;
      }
      v6 = 58;
LABEL_11:
      v10 = v8;
      for ( i = v5; *i == 32; ++i )
        ;
      if ( !v8 )
      {
        v12 = -1;
        do
          ++v12;
        while ( i[v12] );
        v10 = (wchar_t *)&i[v12];
      }
      if ( v10 == i )
        goto LABEL_28;
      for ( j = v10 - 1; *j == 32; --j )
        --v10;
      *v10 = 0;
      v4 = ENABLE_PROTOCOL_LIST::AddProtocolToList(this, i);
      if ( v4 >= 0 )
      {
LABEL_28:
        v14 = v8 + 1;
        if ( !v8 )
          v14 = v5;
        v5 = v14;
        if ( v8 )
          continue;
      }
      goto LABEL_25;
    }
    v9 = v6;
    goto LABEL_10;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\enable_protocol_list.cxx",
      211,
      "ENABLE_PROTOCOL_LIST::AddToList",
      v4,
      "Failed to make a copy of the enabled protocols to work with \n");
LABEL_25:
  STRU::~STRU((STRU *)v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800408b0  mov     [rsp+arg_10], rbx
0x1800408b5  mov     [rsp+arg_18], rbp
0x1800408ba  push    rsi
0x1800408bb  push    rdi
0x1800408bc  push    r12
0x1800408be  push    r14
0x1800408c0  push    r15
0x1800408c2  sub     rsp, 280h
0x1800408c9  mov     rax, cs:__security_cookie
0x1800408d0  xor     rax, rsp
0x1800408d3  mov     [rsp+2A8h+var_38], rax
0x1800408db  mov     rbx, rdx
0x1800408de  mov     r14, rcx
0x1800408e1  xor     edx, edx; Val
0x1800408e3  lea     rcx, [rsp+2A8h+var_238]; void *
0x1800408e8  mov     r8d, 200h; Size
0x1800408ee  call    memset_0
0x1800408f3  mov     r8d, 100h
0x1800408f9  lea     rdx, [rsp+2A8h+var_238]
0x1800408fe  lea     rcx, [rsp+2A8h+var_278]
0x180040903  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180040909  mov     rdx, rbx
0x18004090c  lea     rcx, [rsp+2A8h+var_278]
0x180040911  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180040917  xor     r12d, r12d
0x18004091a  mov     esi, eax
0x18004091c  test    eax, eax
0x18004091e  jns     short loc_180040963
0x180040920  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180040927  jz      loc_180040A19
0x18004092d  mov     rcx, cs:g_pDebug
0x180040934  lea     rax, aFailedToMakeAC; "Failed to make a copy of the enabled pr"...
0x18004093b  mov     [rsp+2A8h+var_280], rax
0x180040940  lea     r9, aEnableProtocol; "ENABLE_PROTOCOL_LIST::AddToList"
0x180040947  mov     r8d, 0D3h
0x18004094d  mov     [rsp+2A8h+var_288], esi
0x180040951  lea     rdx, aServercommonIn_18; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180040958  call    cs:__imp_PuDbgPrintError
0x18004095e  jmp     loc_180040A19
0x180040963  mov     rdi, [rsp+2A8h+Str]
0x180040968  mov     r15d, 20h ; ' '
0x18004096e  movzx   ebp, r15w
0x180040972  mov     rcx, rdi; Str
0x180040975  cmp     bp, r15w
0x180040979  jnz     short loc_1800409A1
0x18004097b  mov     edx, 3Ah ; ':'; Ch
0x180040980  call    cs:__imp_wcschr
0x180040986  mov     rbx, rax
0x180040989  test    rax, rax
0x18004098c  jz      short loc_180040995
0x18004098e  mov     ebp, 3Ah ; ':'
0x180040993  jmp     short loc_1800409AD
0x180040995  mov     ebp, 2Ch ; ','
0x18004099a  mov     rcx, rdi
0x18004099d  mov     edx, ebp
0x18004099f  jmp     short loc_1800409A4
0x1800409a1  movzx   edx, bp; Ch
0x1800409a4  call    cs:__imp_wcschr
0x1800409aa  mov     rbx, rax
0x1800409ad  mov     rcx, rbx
0x1800409b0  mov     rdx, rdi
0x1800409b3  cmp     [rdi], r15w
0x1800409b7  jnz     short loc_1800409C3
0x1800409b9  add     rdx, 2; unsigned __int16 *
0x1800409bd  cmp     [rdx], r15w
0x1800409c1  jz      short loc_1800409B9
0x1800409c3  test    rbx, rbx
0x1800409c6  jnz     short loc_1800409DA
0x1800409c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800409cc  inc     rax
0x1800409cf  cmp     [rdx+rax*2], r12w
0x1800409d4  jnz     short loc_1800409CC
0x1800409d6  lea     rcx, [rdx+rax*2]
0x1800409da  cmp     rcx, rdx
0x1800409dd  jz      short loc_180040A05
0x1800409df  lea     rax, [rcx-2]
0x1800409e3  jmp     short loc_1800409ED
0x1800409e5  lea     rax, [rax-2]
0x1800409e9  sub     rcx, 2
0x1800409ed  cmp     [rax], r15w
0x1800409f1  jz      short loc_1800409E5
0x1800409f3  mov     [rcx], r12w
0x1800409f7  mov     rcx, r14; this
0x1800409fa  call    ?AddProtocolToList@ENABLE_PROTOCOL_LIST@@AEAAJPEBG@Z; ENABLE_PROTOCOL_LIST::AddProtocolToList(ushort const *)
0x1800409ff  mov     esi, eax
0x180040a01  test    eax, eax
0x180040a03  js      short loc_180040A19
0x180040a05  test    rbx, rbx
0x180040a08  lea     rax, [rbx+2]
0x180040a0c  cmovz   rax, rdi
0x180040a10  mov     rdi, rax
0x180040a13  jnz     loc_180040972
0x180040a19  lea     rcx, [rsp+2A8h+var_278]
0x180040a1e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180040a24  mov     eax, esi
0x180040a26  mov     rcx, [rsp+2A8h+var_38]
0x180040a2e  xor     rcx, rsp; StackCookie
0x180040a31  call    __security_check_cookie
0x180040a36  lea     r11, [rsp+2A8h+var_28]
0x180040a3e  mov     rbx, [r11+40h]
0x180040a42  mov     rbp, [r11+48h]
0x180040a46  mov     rsp, r11
0x180040a49  pop     r15
0x180040a4b  pop     r14
0x180040a4d  pop     r12
0x180040a4f  pop     rdi
0x180040a50  pop     rsi
0x180040a51  retn
```
