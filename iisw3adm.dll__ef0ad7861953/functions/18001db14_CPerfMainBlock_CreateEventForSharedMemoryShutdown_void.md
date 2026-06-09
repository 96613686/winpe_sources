# CPerfMainBlock::CreateEventForSharedMemoryShutdown(void)

- ea: `0x18001db14`
- end: `0x18001dd7e`
- name: `?CreateEventForSharedMemoryShutdown@CPerfMainBlock@@QEAAJXZ`
- size: `618`
- prototype: `__int64 __fastcall(CPerfMainBlock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e7b0`

## callees

- `0x18001297c`
- `0x18001db14`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dc90`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dc90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dcc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dcc7`
- `RPCRT4!RpcStringFreeW` at `0x18001dc7a`
- `RPCRT4!RpcStringFreeW` at `0x18001dc7a`
- `RPCRT4!UuidToStringW` at `0x18001dbf7`
- `RPCRT4!UuidToStringW` at `0x18001dbf7`
- `RPCRT4!UuidCreate` at `0x18001dbd9`
- `RPCRT4!UuidCreate` at `0x18001dbd9`

## pseudocode

```c
__int64 __fastcall CPerfMainBlock::CreateEventForSharedMemoryShutdown(CPerfMainBlock *this)
{
  const wchar_t *v1; // r9
  _WORD *v2; // rdx
  __int64 v3; // rdi
  __int64 v5; // rax
  __int64 v6; // r8
  _WORD *v7; // rcx
  unsigned int v8; // ebx
  int v9; // r14d
  __int64 v10; // rax
  const wchar_t *v11; // rcx
  __int64 v12; // rdx
  WCHAR *v13; // r8
  WCHAR *v14; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  WCHAR *v17; // rdx
  _WORD *v18; // rax
  __int64 v19; // rcx
  _WORD *v20; // rcx
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-E0h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Name[1024]; // [rsp+40h] [rbp-C0h] BYREF

  v1 = L"NOT SET";
  v2 = (_WORD *)(*((_QWORD *)this + 1313) + 8364LL);
  v3 = 1024;
  v5 = 7;
  v6 = 1024;
  do
  {
    if ( !v5 )
      break;
    if ( !*v1 )
      break;
    *v2++ = *v1++;
    --v5;
    --v6;
  }
  while ( v6 );
  v7 = v2 - 1;
  v8 = v6 == 0 ? 0x8007007A : 0;
  if ( v6 )
    v7 = v2;
  *v7 = 0;
  if ( v6 )
  {
    v9 = 0;
    *(_WORD *)(*((_QWORD *)this + 1313) + 10410LL) = 0;
    while ( 1 )
    {
      StringUuid = 0;
      Uuid = 0;
      if ( UuidCreate(&Uuid) || UuidToStringW(&Uuid, &StringUuid) )
      {
        v8 = -2147023893;
      }
      else
      {
        v10 = 2147483646;
        v11 = L"Global\\ASP_PERFMON_-";
        v12 = 1024;
        v13 = Name;
        do
        {
          if ( !v10 )
            break;
          if ( !*v11 )
            break;
          *v13++ = *v11++;
          --v10;
          --v12;
        }
        while ( v12 );
        v14 = v13 - 1;
        v8 = v12 == 0 ? 0x8007007A : 0;
        if ( v12 )
          v14 = v13;
        *v14 = 0;
        if ( v12 )
          v8 = StringCchCatW(Name, 0x400u, StringUuid);
      }
      if ( StringUuid )
        RpcStringFreeW(&StringUuid);
      EventW = CreateEventW((LPSECURITY_ATTRIBUTES)((char *)this + 16), 1, 0, Name);
      *((_QWORD *)this + 9) = EventW;
      if ( EventW )
      {
        if ( GetLastError() == 183 )
        {
          CloseHandle(*((HANDLE *)this + 9));
          *((_QWORD *)this + 9) = 0;
          v8 = -2147024713;
        }
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( *((_QWORD *)this + 9) )
        break;
      if ( (unsigned int)++v9 >= 0xA )
        return v8;
    }
    v17 = Name;
    v18 = (_WORD *)(*((_QWORD *)this + 1313) + 8364LL);
    v19 = 1023;
    do
    {
      if ( !v19 )
        break;
      if ( !*v17 )
        break;
      *v18++ = *v17++;
      --v19;
      --v3;
    }
    while ( v3 );
    v20 = v18 - 1;
    if ( v3 )
      v20 = v18;
    *v20 = 0;
    v8 = v3 == 0 ? 0x8007007A : 0;
    *(_WORD *)(*((_QWORD *)this + 1313) + 10410LL) = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18001db14  mov     [rsp-8+arg_8], rbx
0x18001db19  mov     [rsp-8+arg_10], rsi
0x18001db1e  push    rbp
0x18001db1f  push    rdi
0x18001db20  push    r12
0x18001db22  push    r14
0x18001db24  push    r15
0x18001db26  lea     rbp, [rsp-750h]
0x18001db2e  sub     rsp, 850h
0x18001db35  mov     rax, cs:__security_cookie
0x18001db3c  xor     rax, rsp
0x18001db3f  mov     [rbp+770h+var_30], rax
0x18001db46  mov     rdx, [rcx+2908h]
0x18001db4d  lea     r9, aNotSet; "NOT SET"
0x18001db54  add     rdx, 20ACh
0x18001db5b  mov     edi, 400h
0x18001db60  xor     r12d, r12d
0x18001db63  mov     rsi, rcx
0x18001db66  mov     eax, 7
0x18001db6b  mov     r8d, edi
0x18001db6e  test    rax, rax
0x18001db71  jz      short loc_18001DB90
0x18001db73  movzx   ecx, word ptr [r9]
0x18001db77  test    cx, cx
0x18001db7a  jz      short loc_18001DB90
0x18001db7c  mov     [rdx], cx
0x18001db7f  add     r9, 2
0x18001db83  add     rdx, 2
0x18001db87  dec     rax
0x18001db8a  sub     r8, 1
0x18001db8e  jnz     short loc_18001DB6E
0x18001db90  mov     rax, r8
0x18001db93  lea     rcx, [rdx-2]
0x18001db97  neg     rax
0x18001db9a  sbb     ebx, ebx
0x18001db9c  not     ebx
0x18001db9e  and     ebx, 8007007Ah
0x18001dba4  test    r8, r8
0x18001dba7  cmovnz  rcx, rdx
0x18001dbab  mov     [rcx], r12w
0x18001dbaf  jz      loc_18001DD51
0x18001dbb5  mov     rcx, [rsi+2908h]
0x18001dbbc  mov     r14d, r12d
0x18001dbbf  mov     [rcx+28AAh], r12w
0x18001dbc7  xorps   xmm0, xmm0
0x18001dbca  mov     [rsp+870h+StringUuid], r12
0x18001dbcf  lea     rcx, [rsp+870h+Uuid]; Uuid
0x18001dbd4  movups  xmmword ptr [rsp+870h+Uuid.Data1], xmm0
0x18001dbd9  call    cs:__imp_UuidCreate
0x18001dbdf  test    eax, eax
0x18001dbe1  jz      short loc_18001DBED
0x18001dbe3  mov     ebx, 800703EBh
0x18001dbe8  jmp     loc_18001DC6E
0x18001dbed  lea     rdx, [rsp+870h+StringUuid]; StringUuid
0x18001dbf2  lea     rcx, [rsp+870h+Uuid]; Uuid
0x18001dbf7  call    cs:__imp_UuidToStringW
0x18001dbfd  test    eax, eax
0x18001dbff  jnz     short loc_18001DBE3
0x18001dc01  mov     eax, 7FFFFFFEh
0x18001dc06  lea     rcx, aGlobalAspPerfm_0; "Global\\ASP_PERFMON_-"
0x18001dc0d  mov     rdx, rdi
0x18001dc10  lea     r8, [rsp+870h+Name]
0x18001dc15  test    rax, rax
0x18001dc18  jz      short loc_18001DC39
0x18001dc1a  movzx   r9d, word ptr [rcx]
0x18001dc1e  test    r9w, r9w
0x18001dc22  jz      short loc_18001DC39
0x18001dc24  mov     [r8], r9w
0x18001dc28  add     rcx, 2
0x18001dc2c  add     r8, 2
0x18001dc30  dec     rax
0x18001dc33  sub     rdx, 1
0x18001dc37  jnz     short loc_18001DC15
0x18001dc39  mov     rax, rdx
0x18001dc3c  lea     rcx, [r8-2]
0x18001dc40  neg     rax
0x18001dc43  sbb     ebx, ebx
0x18001dc45  not     ebx
0x18001dc47  and     ebx, 8007007Ah
0x18001dc4d  test    rdx, rdx
0x18001dc50  cmovnz  rcx, r8
0x18001dc54  mov     [rcx], r12w
0x18001dc58  jz      short loc_18001DC6E
0x18001dc5a  mov     r8, [rsp+870h+StringUuid]; unsigned __int16 *
0x18001dc5f  lea     rcx, [rsp+870h+Name]; unsigned __int16 *
0x18001dc64  mov     rdx, rdi; unsigned __int64
0x18001dc67  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001dc6c  mov     ebx, eax
0x18001dc6e  cmp     [rsp+870h+StringUuid], r12
0x18001dc73  jz      short loc_18001DC80
0x18001dc75  lea     rcx, [rsp+870h+StringUuid]; String
0x18001dc7a  call    cs:__imp_RpcStringFreeW
0x18001dc80  xor     r8d, r8d; bInitialState
0x18001dc83  lea     r9, [rsp+870h+Name]; lpName
0x18001dc88  lea     rcx, [rsi+10h]; lpEventAttributes
0x18001dc8c  lea     edx, [r8+1]; bManualReset
0x18001dc90  call    cs:__imp_CreateEventW
0x18001dc96  mov     [rsi+48h], rax
0x18001dc9a  test    rax, rax
0x18001dc9d  jnz     short loc_18001DCB6
0x18001dc9f  call    cs:__imp_GetLastError
0x18001dca5  mov     ebx, eax
0x18001dca7  test    eax, eax
0x18001dca9  jle     short loc_18001DCD6
0x18001dcab  movzx   ebx, ax
0x18001dcae  or      ebx, 80070000h
0x18001dcb4  jmp     short loc_18001DCD6
0x18001dcb6  call    cs:__imp_GetLastError
0x18001dcbc  cmp     eax, 0B7h
0x18001dcc1  jnz     short loc_18001DCD6
0x18001dcc3  mov     rcx, [rsi+48h]; hObject
0x18001dcc7  call    cs:__imp_CloseHandle
0x18001dccd  mov     [rsi+48h], r12
0x18001dcd1  mov     ebx, 800700B7h
0x18001dcd6  cmp     [rsi+48h], r12
0x18001dcda  jnz     short loc_18001DCEB
0x18001dcdc  inc     r14d
0x18001dcdf  cmp     r14d, 0Ah
0x18001dce3  jb      loc_18001DBC7
0x18001dce9  jmp     short loc_18001DD51
0x18001dceb  mov     rax, [rsi+2908h]
0x18001dcf2  lea     rdx, [rsp+870h+Name]
0x18001dcf7  add     rax, 20ACh
0x18001dcfd  mov     ecx, 3FFh
0x18001dd02  test    rcx, rcx
0x18001dd05  jz      short loc_18001DD26
0x18001dd07  movzx   r8d, word ptr [rdx]
0x18001dd0b  test    r8w, r8w
0x18001dd0f  jz      short loc_18001DD26
0x18001dd11  mov     [rax], r8w
0x18001dd15  add     rdx, 2
0x18001dd19  add     rax, 2
0x18001dd1d  dec     rcx
0x18001dd20  sub     rdi, 1
0x18001dd24  jnz     short loc_18001DD02
0x18001dd26  test    rdi, rdi
0x18001dd29  lea     rcx, [rax-2]
0x18001dd2d  cmovnz  rcx, rax
0x18001dd31  neg     rdi
0x18001dd34  sbb     ebx, ebx
0x18001dd36  not     ebx
0x18001dd38  mov     [rcx], r12w
0x18001dd3c  and     ebx, 8007007Ah
0x18001dd42  mov     rcx, [rsi+2908h]
0x18001dd49  mov     [rcx+28AAh], r12w
0x18001dd51  mov     eax, ebx
0x18001dd53  mov     rcx, [rbp+770h+var_30]
0x18001dd5a  xor     rcx, rsp; StackCookie
0x18001dd5d  call    __security_check_cookie
0x18001dd62  lea     r11, [rsp+870h+var_20]
0x18001dd6a  mov     rbx, [r11+38h]
0x18001dd6e  mov     rsi, [r11+40h]
0x18001dd72  mov     rsp, r11
0x18001dd75  pop     r15
0x18001dd77  pop     r14
0x18001dd79  pop     r12
0x18001dd7b  pop     rdi
0x18001dd7c  pop     rbp
0x18001dd7d  retn
```
