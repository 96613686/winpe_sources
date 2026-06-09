# CEXTLOG::ReadFileLogRecord(_iobuf *,_INETLOGLINE *,char *,ulong)

- ea: `0x180005e90`
- end: `0x180006612`
- name: `?ReadFileLogRecord@CEXTLOG@@MEAAJPEAU_iobuf@@PEAU_INETLOGLINE@@PEADK@Z`
- size: `1922`
- prototype: `int(CEXTLOG *__hidden this, struct _iobuf *, struct _INETLOGLINE *, char *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180005e90`
- `0x18000eca0`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180005f55`
- `msvcrt!strcpy_s` at `0x180005f82`
- `msvcrt!strcpy_s` at `0x1800062a0`
- `msvcrt!strcpy_s` at `0x180005f55`
- `msvcrt!strcpy_s` at `0x180005f82`
- `msvcrt!strcpy_s` at `0x1800062a0`
- `msvcrt!_stricmp` at `0x180006018`
- `msvcrt!_stricmp` at `0x180006037`
- `msvcrt!_stricmp` at `0x180006056`
- `msvcrt!_stricmp` at `0x180006075`
- `msvcrt!_stricmp` at `0x180006094`
- `msvcrt!_stricmp` at `0x1800060b3`
- `msvcrt!_stricmp` at `0x1800060d2`
- `msvcrt!_stricmp` at `0x1800060f1`
- `msvcrt!_stricmp` at `0x180006110`
- `msvcrt!_stricmp` at `0x18000612f`
- `msvcrt!_stricmp` at `0x18000614e`
- `msvcrt!_stricmp` at `0x18000616d`
- `msvcrt!_stricmp` at `0x18000618c`
- `msvcrt!_stricmp` at `0x1800061ab`
- `msvcrt!_stricmp` at `0x1800061ca`
- `msvcrt!_stricmp` at `0x1800061e9`
- `msvcrt!_stricmp` at `0x180006208`
- `msvcrt!_stricmp` at `0x180006227`
- `msvcrt!_stricmp` at `0x180006243`
- `msvcrt!_stricmp` at `0x18000625f`
- `msvcrt!_stricmp` at `0x180006018`
- `msvcrt!_stricmp` at `0x180006037`
- `msvcrt!_stricmp` at `0x180006056`
- `msvcrt!_stricmp` at `0x180006075`
- `msvcrt!_stricmp` at `0x180006094`
- `msvcrt!_stricmp` at `0x1800060b3`
- `msvcrt!_stricmp` at `0x1800060d2`
- `msvcrt!_stricmp` at `0x1800060f1`
- `msvcrt!_stricmp` at `0x180006110`
- `msvcrt!_stricmp` at `0x18000612f`
- `msvcrt!_stricmp` at `0x18000614e`
- `msvcrt!_stricmp` at `0x18000616d`
- `msvcrt!_stricmp` at `0x18000618c`
- `msvcrt!_stricmp` at `0x1800061ab`
- `msvcrt!_stricmp` at `0x1800061ca`
- `msvcrt!_stricmp` at `0x1800061e9`
- `msvcrt!_stricmp` at `0x180006208`
- `msvcrt!_stricmp` at `0x180006227`
- `msvcrt!_stricmp` at `0x180006243`
- `msvcrt!_stricmp` at `0x18000625f`
- `msvcrt!fgets` at `0x180005ecd`
- `msvcrt!fgets` at `0x1800062cc`
- `msvcrt!fgets` at `0x180005ecd`
- `msvcrt!fgets` at `0x1800062cc`
- `msvcrt!strstr` at `0x180005f21`
- `msvcrt!strstr` at `0x180005f97`
- `msvcrt!strstr` at `0x180005f21`
- `msvcrt!strstr` at `0x180005f97`
- `msvcrt!strtok` at `0x180005f37`
- `msvcrt!strtok` at `0x180005f64`
- `msvcrt!strtok` at `0x180005ffe`
- `msvcrt!strtok` at `0x1800062b1`
- `msvcrt!strtok` at `0x180006313`
- `msvcrt!strtok` at `0x180006494`
- `msvcrt!strtok` at `0x180005f37`
- `msvcrt!strtok` at `0x180005f64`
- `msvcrt!strtok` at `0x180005ffe`
- `msvcrt!strtok` at `0x1800062b1`
- `msvcrt!strtok` at `0x180006313`
- `msvcrt!strtok` at `0x180006494`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x1800065fc`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x1800065fc`

## string_xrefs

- `0x1800060a9`: `s-computername`
- `0x180006106`: `cs-uri-stem`
- `0x180006125`: `cs-uri-query`
- `0x180006239`: `cs(User-Agent)`

## pseudocode

```c
__int64 __fastcall CEXTLOG::ReadFileLogRecord(
        CEXTLOG *this,
        struct _iobuf *a2,
        struct _INETLOGLINE *a3,
        char *a4,
        int MaxCount)
{
  char *i; // rax
  char *j; // rcx
  __int64 v11; // rdx
  char *v12; // rax
  char *v13; // rax
  char *v14; // rax
  char *v15; // rax
  char *v16; // rax
  int k; // ebp
  __int64 v18; // rcx
  const char *v19; // rdi
  char *v21; // rbp
  char *v22; // r14
  char *v23; // rax
  int v24; // edi
  unsigned int v25; // r15d
  __int64 v26; // rax
  char *v27; // rcx
  char *v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  bool v31; // zf
  WORD v32; // cx
  WORD v33; // ax
  WORD v34; // cx
  char *v35; // rdx
  WORD v36; // ax
  WORD v37; // cx
  char *v38; // rcx
  __int16 v39; // ax
  char *v40; // rdx
  WORD v41; // ax
  WORD v42; // cx
  WORD v43; // ax
  WORD v44; // cx
  struct _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-68h] BYREF

  for ( i = fgets(a4, MaxCount, a2); ; i = fgets(a4, MaxCount, a2) )
  {
    if ( !i )
      return 2147500037LL;
    for ( j = a4; (unsigned __int8)*j <= 0x20u; ++j )
    {
      v11 = 0x100002200LL;
      if ( !_bittest64(&v11, *j) )
        break;
    }
    if ( *j != 10 && *j )
      break;
LABEL_59:
    ;
  }
  if ( *j == 35 )
  {
    v12 = strstr(a4, "#Date:");
    if ( v12 )
    {
      v13 = strtok(v12 + 6, " \t\r\n");
      if ( !v13 )
        return 2147500037LL;
      strcpy_s((char *)this + 2256, 0xFu, v13);
      v14 = strtok(0, " \t\r\n");
      if ( !v14 )
        return 2147500037LL;
      strcpy_s((char *)this + 2271, 0xFu, v14);
    }
    else
    {
      v15 = strstr(a4, "#Fields:");
      if ( v15 )
      {
        *((_QWORD *)this + 286) = 0;
        *((_QWORD *)this + 287) = 0;
        *((_QWORD *)this + 288) = 0;
        *((_QWORD *)this + 289) = 0;
        *((_QWORD *)this + 290) = 0;
        *((_QWORD *)this + 291) = 0;
        *((_QWORD *)this + 292) = 0;
        *((_QWORD *)this + 293) = 0;
        *((_QWORD *)this + 294) = 0;
        *((_QWORD *)this + 295) = 0;
        *((_DWORD *)a3 + 40) = 0;
        v16 = strtok(v15 + 8, " \t\r\n");
        for ( k = 1; ; ++k )
        {
          v19 = v16;
          if ( !v16 )
            break;
          if ( !_stricmp(v16, "date") )
          {
            *((_DWORD *)this + 572) = k;
          }
          else if ( !_stricmp(v19, "time") )
          {
            *((_DWORD *)this + 573) = k;
          }
          else if ( !_stricmp(v19, "c-ip") )
          {
            *((_DWORD *)this + 574) = k;
          }
          else if ( !_stricmp(v19, "cs-username") )
          {
            *((_DWORD *)this + 575) = k;
          }
          else if ( !_stricmp(v19, "s-sitename") )
          {
            *((_DWORD *)this + 576) = k;
          }
          else if ( !_stricmp(v19, "s-computername") )
          {
            *((_DWORD *)this + 577) = k;
          }
          else if ( !_stricmp(v19, "s-ip") )
          {
            *((_DWORD *)this + 578) = k;
          }
          else if ( !_stricmp(v19, "cs-method") )
          {
            *((_DWORD *)this + 579) = k;
          }
          else if ( !_stricmp(v19, "cs-uri-stem") )
          {
            *((_DWORD *)this + 580) = k;
          }
          else if ( !_stricmp(v19, "cs-uri-query") )
          {
            *((_DWORD *)this + 581) = k;
          }
          else if ( !_stricmp(v19, "sc-status") )
          {
            *((_DWORD *)this + 582) = k;
          }
          else if ( !_stricmp(v19, "sc-win32-status") )
          {
            *((_DWORD *)this + 583) = k;
          }
          else if ( !_stricmp(v19, "sc-bytes") )
          {
            *((_DWORD *)this + 584) = k;
          }
          else if ( !_stricmp(v19, "cs-bytes") )
          {
            *((_DWORD *)this + 585) = k;
          }
          else if ( !_stricmp(v19, "time-taken") )
          {
            *((_DWORD *)this + 586) = k;
          }
          else if ( !_stricmp(v19, "s-port") )
          {
            *((_DWORD *)this + 587) = k;
          }
          else if ( !_stricmp(v19, "cs-version") )
          {
            *((_DWORD *)this + 588) = k;
          }
          else if ( !_stricmp(v19, "cs(Cookie)") )
          {
            *((_DWORD *)this + 589) = k;
          }
          else if ( !_stricmp(v19, "cs(User-Agent)") )
          {
            *((_DWORD *)this + 590) = k;
          }
          else if ( !_stricmp(v19, "cs(Referer)") )
          {
            *((_DWORD *)this + 591) = k;
          }
          else
          {
            v18 = *((int *)a3 + 40);
            if ( (int)v18 < 20 )
            {
              *((_DWORD *)a3 + 40) = v18 + 1;
              strcpy_s((char *)a3 + 32 * v18 + 8 * v18 + 168, 0x20u, v19);
            }
          }
          v16 = strtok(0, " \t\r\n");
        }
      }
    }
    goto LABEL_59;
  }
  v21 = (char *)this + 2256;
  v22 = (char *)this + 2271;
  v23 = strtok(a4, " \t\r\n");
  v24 = 1;
  v25 = 0;
  while ( 1 )
  {
    v27 = v23;
    if ( !v23 )
      break;
    if ( v24 == *((_DWORD *)this + 572) )
    {
      v21 = v23;
    }
    else if ( v24 == *((_DWORD *)this + 573) )
    {
      v22 = v23;
    }
    else if ( v24 == *((_DWORD *)this + 574) )
    {
      *(_QWORD *)a3 = v23;
    }
    else if ( v24 == *((_DWORD *)this + 575) )
    {
      *((_QWORD *)a3 + 1) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 576) )
    {
      *((_QWORD *)a3 + 15) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 577) )
    {
      *((_QWORD *)a3 + 16) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 578) )
    {
      *((_QWORD *)a3 + 2) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 579) )
    {
      *((_QWORD *)a3 + 3) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 580) )
    {
      *((_QWORD *)a3 + 4) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 581) )
    {
      *((_QWORD *)a3 + 5) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 582) )
    {
      *((_QWORD *)a3 + 12) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 583) )
    {
      *((_QWORD *)a3 + 11) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 584) )
    {
      *((_QWORD *)a3 + 8) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 585) )
    {
      *((_QWORD *)a3 + 9) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 586) )
    {
      *((_QWORD *)a3 + 10) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 587) )
    {
      *((_QWORD *)a3 + 13) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 588) )
    {
      *((_QWORD *)a3 + 6) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 589) )
    {
      *((_QWORD *)a3 + 18) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 590) )
    {
      *((_QWORD *)a3 + 17) = v23;
    }
    else if ( v24 == *((_DWORD *)this + 591) )
    {
      *((_QWORD *)a3 + 19) = v23;
    }
    else if ( v25 < *((_DWORD *)a3 + 40) )
    {
      v26 = v25++ + 5LL;
      *((_QWORD *)a3 + 5 * v26) = v27;
    }
    ++v24;
    v23 = strtok(0, " \t\r\n");
  }
  v28 = v21 + 6;
  v29 = (unsigned __int16)(v21[3] + 10 * (v21[2] + 10 * (v21[1] + 10 * *v21)) + 12208);
  v30 = (unsigned __int16)(v21[5] - 48);
  v31 = v21[6] == 47;
  SystemTime = 0;
  SystemTime.wYear = v29;
  v32 = v30;
  if ( v31 )
    v28 = v21 + 5;
  else
    v32 = *v28 + 10 * v30 - 48;
  v33 = v28[2] - 48;
  SystemTime.wMonth = v32;
  v34 = v33;
  if ( v28[3] != 47 )
    v34 = v28[3] + 10 * v33 - 48;
  v35 = v22 + 1;
  v36 = *v22 - 48;
  SystemTime.wDay = v34;
  v37 = v36;
  if ( v22[1] == 58 )
    v35 = v22;
  else
    v37 = *v35 + 10 * v36 - 48;
  SystemTime.wHour = v37;
  v38 = v35 + 2;
  v39 = v35[2];
  v40 = v35 + 3;
  v41 = v39 - 48;
  if ( *v40 == 58 )
  {
    v40 = v38;
    v42 = v41;
  }
  else
  {
    v42 = *v40 + 10 * v41 - 48;
  }
  v43 = v40[2] - 48;
  SystemTime.wMinute = v42;
  v44 = v43;
  if ( v40[3] )
    v44 = v40[3] + 10 * v43 - 48;
  SystemTime.wSecond = v44;
  return SystemTimeToVariantTime(&SystemTime, (DOUBLE *)a3 + 14) == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180005e90  push    rbx
0x180005e92  push    rbp
0x180005e93  push    rsi
0x180005e94  push    rdi
0x180005e95  push    r12
0x180005e97  push    r13
0x180005e99  push    r14
0x180005e9b  push    r15
0x180005e9d  sub     rsp, 48h
0x180005ea1  mov     rax, cs:__security_cookie
0x180005ea8  xor     rax, rsp
0x180005eab  mov     [rsp+88h+var_58], rax
0x180005eb0  mov     r12d, [rsp+88h+MaxCount]
0x180005eb8  mov     rsi, r8
0x180005ebb  mov     r8, rdx; Stream
0x180005ebe  mov     r14, rdx
0x180005ec1  mov     rbx, rcx
0x180005ec4  mov     edx, r12d; MaxCount
0x180005ec7  mov     rcx, r9; Buffer
0x180005eca  mov     r15, r9
0x180005ecd  call    cs:__imp_fgets
0x180005ed3  xor     r13d, r13d
0x180005ed6  jmp     loc_1800062D2
0x180005edb  mov     rcx, r15
0x180005ede  cmp     byte ptr [rcx], 20h ; ' '
0x180005ee1  ja      short loc_180005EFC
0x180005ee3  movsx   rax, byte ptr [rcx]
0x180005ee7  mov     rdx, 100002200h
0x180005ef1  bt      rdx, rax
0x180005ef5  jnb     short loc_180005EFC
0x180005ef7  inc     rcx
0x180005efa  jmp     short loc_180005EDE
0x180005efc  cmp     byte ptr [rcx], 0Ah
0x180005eff  jz      loc_1800062C3
0x180005f05  cmp     [rcx], r13b
0x180005f08  jz      loc_1800062C3
0x180005f0e  cmp     byte ptr [rcx], 23h ; '#'
0x180005f11  mov     rcx, r15; String
0x180005f14  jnz     loc_1800062FE
0x180005f1a  lea     rdx, SubStr; "#Date:"
0x180005f21  call    cs:__imp_strstr
0x180005f27  test    rax, rax
0x180005f2a  jz      short loc_180005F8D
0x180005f2c  lea     rcx, [rax+6]; String
0x180005f30  lea     rdx, Delimiter; " \t\r\n"
0x180005f37  call    cs:__imp_strtok
0x180005f3d  test    rax, rax
0x180005f40  jz      loc_1800062DB
0x180005f46  lea     rcx, [rbx+8D0h]; Destination
0x180005f4d  mov     r8, rax; Source
0x180005f50  mov     edx, 0Fh; SizeInBytes
0x180005f55  call    cs:__imp_strcpy_s
0x180005f5b  lea     rdx, Delimiter; " \t\r\n"
0x180005f62  xor     ecx, ecx; String
0x180005f64  call    cs:__imp_strtok
0x180005f6a  test    rax, rax
0x180005f6d  jz      loc_1800062DB
0x180005f73  lea     rcx, [rbx+8DFh]; Destination
0x180005f7a  mov     r8, rax; Source
0x180005f7d  mov     edx, 0Fh; SizeInBytes
0x180005f82  call    cs:__imp_strcpy_s
0x180005f88  jmp     loc_1800062C3
0x180005f8d  lea     rdx, aFields; "#Fields:"
0x180005f94  mov     rcx, r15; Str
0x180005f97  call    cs:__imp_strstr
0x180005f9d  test    rax, rax
0x180005fa0  jz      loc_1800062C3
0x180005fa6  mov     [rbx+8F0h], r13
0x180005fad  lea     rcx, [rax+8]; String
0x180005fb1  mov     [rbx+8F8h], r13
0x180005fb8  lea     rdx, Delimiter; " \t\r\n"
0x180005fbf  mov     [rbx+900h], r13
0x180005fc6  mov     [rbx+908h], r13
0x180005fcd  mov     [rbx+910h], r13
0x180005fd4  mov     [rbx+918h], r13
0x180005fdb  mov     [rbx+920h], r13
0x180005fe2  mov     [rbx+928h], r13
0x180005fe9  mov     [rbx+930h], r13
0x180005ff0  mov     [rbx+938h], r13
0x180005ff7  mov     [rsi+0A0h], r13d
0x180005ffe  call    cs:__imp_strtok
0x180006004  mov     ebp, 1
0x180006009  jmp     loc_1800062B7
0x18000600e  lea     rdx, String2; "date"
0x180006015  mov     rcx, rdi; String1
0x180006018  call    cs:__imp__stricmp
0x18000601e  test    eax, eax
0x180006020  jnz     short loc_18000602D
0x180006022  mov     [rbx+8F0h], ebp
0x180006028  jmp     loc_1800062A6
0x18000602d  lea     rdx, aTime; "time"
0x180006034  mov     rcx, rdi; String1
0x180006037  call    cs:__imp__stricmp
0x18000603d  test    eax, eax
0x18000603f  jnz     short loc_18000604C
0x180006041  mov     [rbx+8F4h], ebp
0x180006047  jmp     loc_1800062A6
0x18000604c  lea     rdx, aCIp; "c-ip"
0x180006053  mov     rcx, rdi; String1
0x180006056  call    cs:__imp__stricmp
0x18000605c  test    eax, eax
0x18000605e  jnz     short loc_18000606B
0x180006060  mov     [rbx+8F8h], ebp
0x180006066  jmp     loc_1800062A6
0x18000606b  lea     rdx, aCsUsername; "cs-username"
0x180006072  mov     rcx, rdi; String1
0x180006075  call    cs:__imp__stricmp
0x18000607b  test    eax, eax
0x18000607d  jnz     short loc_18000608A
0x18000607f  mov     [rbx+8FCh], ebp
0x180006085  jmp     loc_1800062A6
0x18000608a  lea     rdx, aSSitename; "s-sitename"
0x180006091  mov     rcx, rdi; String1
0x180006094  call    cs:__imp__stricmp
0x18000609a  test    eax, eax
0x18000609c  jnz     short loc_1800060A9
0x18000609e  mov     [rbx+900h], ebp
0x1800060a4  jmp     loc_1800062A6
0x1800060a9  lea     rdx, aSComputername; "s-computername"
0x1800060b0  mov     rcx, rdi; String1
0x1800060b3  call    cs:__imp__stricmp
0x1800060b9  test    eax, eax
0x1800060bb  jnz     short loc_1800060C8
0x1800060bd  mov     [rbx+904h], ebp
0x1800060c3  jmp     loc_1800062A6
0x1800060c8  lea     rdx, aSIp; "s-ip"
0x1800060cf  mov     rcx, rdi; String1
0x1800060d2  call    cs:__imp__stricmp
0x1800060d8  test    eax, eax
0x1800060da  jnz     short loc_1800060E7
0x1800060dc  mov     [rbx+908h], ebp
0x1800060e2  jmp     loc_1800062A6
0x1800060e7  lea     rdx, aCsMethod; "cs-method"
0x1800060ee  mov     rcx, rdi; String1
0x1800060f1  call    cs:__imp__stricmp
0x1800060f7  test    eax, eax
0x1800060f9  jnz     short loc_180006106
0x1800060fb  mov     [rbx+90Ch], ebp
0x180006101  jmp     loc_1800062A6
0x180006106  lea     rdx, aCsUriStem; "cs-uri-stem"
0x18000610d  mov     rcx, rdi; String1
0x180006110  call    cs:__imp__stricmp
0x180006116  test    eax, eax
0x180006118  jnz     short loc_180006125
0x18000611a  mov     [rbx+910h], ebp
0x180006120  jmp     loc_1800062A6
0x180006125  lea     rdx, aCsUriQuery; "cs-uri-query"
0x18000612c  mov     rcx, rdi; String1
0x18000612f  call    cs:__imp__stricmp
0x180006135  test    eax, eax
0x180006137  jnz     short loc_180006144
0x180006139  mov     [rbx+914h], ebp
0x18000613f  jmp     loc_1800062A6
0x180006144  lea     rdx, aScStatus; "sc-status"
0x18000614b  mov     rcx, rdi; String1
0x18000614e  call    cs:__imp__stricmp
0x180006154  test    eax, eax
0x180006156  jnz     short loc_180006163
0x180006158  mov     [rbx+918h], ebp
0x18000615e  jmp     loc_1800062A6
0x180006163  lea     rdx, aScWin32Status; "sc-win32-status"
0x18000616a  mov     rcx, rdi; String1
0x18000616d  call    cs:__imp__stricmp
0x180006173  test    eax, eax
0x180006175  jnz     short loc_180006182
0x180006177  mov     [rbx+91Ch], ebp
0x18000617d  jmp     loc_1800062A6
0x180006182  lea     rdx, aScBytes; "sc-bytes"
0x180006189  mov     rcx, rdi; String1
0x18000618c  call    cs:__imp__stricmp
0x180006192  test    eax, eax
0x180006194  jnz     short loc_1800061A1
0x180006196  mov     [rbx+920h], ebp
0x18000619c  jmp     loc_1800062A6
0x1800061a1  lea     rdx, aCsBytes; "cs-bytes"
0x1800061a8  mov     rcx, rdi; String1
0x1800061ab  call    cs:__imp__stricmp
0x1800061b1  test    eax, eax
0x1800061b3  jnz     short loc_1800061C0
0x1800061b5  mov     [rbx+924h], ebp
0x1800061bb  jmp     loc_1800062A6
0x1800061c0  lea     rdx, aTimeTaken; "time-taken"
0x1800061c7  mov     rcx, rdi; String1
0x1800061ca  call    cs:__imp__stricmp
0x1800061d0  test    eax, eax
0x1800061d2  jnz     short loc_1800061DF
0x1800061d4  mov     [rbx+928h], ebp
0x1800061da  jmp     loc_1800062A6
0x1800061df  lea     rdx, aSPort; "s-port"
0x1800061e6  mov     rcx, rdi; String1
0x1800061e9  call    cs:__imp__stricmp
0x1800061ef  test    eax, eax
0x1800061f1  jnz     short loc_1800061FE
0x1800061f3  mov     [rbx+92Ch], ebp
0x1800061f9  jmp     loc_1800062A6
0x1800061fe  lea     rdx, aCsVersion; "cs-version"
0x180006205  mov     rcx, rdi; String1
0x180006208  call    cs:__imp__stricmp
0x18000620e  test    eax, eax
0x180006210  jnz     short loc_18000621D
0x180006212  mov     [rbx+930h], ebp
0x180006218  jmp     loc_1800062A6
0x18000621d  lea     rdx, aCsCookie; "cs(Cookie)"
0x180006224  mov     rcx, rdi; String1
0x180006227  call    cs:__imp__stricmp
0x18000622d  test    eax, eax
0x18000622f  jnz     short loc_180006239
0x180006231  mov     [rbx+934h], ebp
0x180006237  jmp     short loc_1800062A6
0x180006239  lea     rdx, aCsUserAgent; "cs(User-Agent)"
0x180006240  mov     rcx, rdi; String1
0x180006243  call    cs:__imp__stricmp
0x180006249  test    eax, eax
0x18000624b  jnz     short loc_180006255
0x18000624d  mov     [rbx+938h], ebp
0x180006253  jmp     short loc_1800062A6
0x180006255  lea     rdx, aCsReferer; "cs(Referer)"
0x18000625c  mov     rcx, rdi; String1
0x18000625f  call    cs:__imp__stricmp
0x180006265  test    eax, eax
0x180006267  jnz     short loc_180006271
0x180006269  mov     [rbx+93Ch], ebp
0x18000626f  jmp     short loc_1800062A6
0x180006271  movsxd  rcx, dword ptr [rsi+0A0h]
0x180006278  cmp     ecx, 14h
0x18000627b  jge     short loc_1800062A6
0x18000627d  lea     eax, [rcx+1]
0x180006280  mov     r8, rdi; Source
0x180006283  mov     [rsi+0A0h], eax
0x180006289  mov     edx, 20h ; ' '; SizeInBytes
0x18000628e  mov     rax, rcx
0x180006291  lea     rcx, ds:15h[rcx*4]
0x180006299  add     rcx, rax
0x18000629c  lea     rcx, [rsi+rcx*8]; Destination
0x1800062a0  call    cs:__imp_strcpy_s
0x1800062a6  inc     ebp
0x1800062a8  lea     rdx, Delimiter; " \t\r\n"
0x1800062af  xor     ecx, ecx; String
0x1800062b1  call    cs:__imp_strtok
0x1800062b7  mov     rdi, rax
0x1800062ba  test    rax, rax
0x1800062bd  jnz     loc_18000600E
0x1800062c3  mov     r8, r14; Stream
0x1800062c6  mov     edx, r12d; MaxCount
0x1800062c9  mov     rcx, r15; Buffer
0x1800062cc  call    cs:__imp_fgets
0x1800062d2  test    rax, rax
0x1800062d5  jnz     loc_180005EDB
0x1800062db  mov     eax, 80004005h
0x1800062e0  mov     rcx, [rsp+88h+var_58]
0x1800062e5  xor     rcx, rsp; StackCookie
0x1800062e8  call    __security_check_cookie
0x1800062ed  add     rsp, 48h
0x1800062f1  pop     r15
0x1800062f3  pop     r14
0x1800062f5  pop     r13
0x1800062f7  pop     r12
0x1800062f9  pop     rdi
0x1800062fa  pop     rsi
0x1800062fb  pop     rbp
0x1800062fc  pop     rbx
0x1800062fd  retn
0x1800062fe  lea     rdx, Delimiter; " \t\r\n"
0x180006305  lea     rbp, [rbx+8D0h]
0x18000630c  lea     r14, [rbx+8DFh]
0x180006313  call    cs:__imp_strtok
0x180006319  mov     edi, 1
0x18000631e  mov     r15d, r13d
0x180006321  jmp     loc_18000649A
0x180006326  cmp     edi, [rbx+8F0h]
0x18000632c  jnz     short loc_180006336
0x18000632e  mov     rbp, rcx
0x180006331  jmp     loc_180006489
0x180006336  cmp     edi, [rbx+8F4h]
0x18000633c  jnz     short loc_180006346
0x18000633e  mov     r14, rcx
0x180006341  jmp     loc_180006489
0x180006346  cmp     edi, [rbx+8F8h]
0x18000634c  jnz     short loc_180006356
0x18000634e  mov     [rsi], rcx
0x180006351  jmp     loc_180006489
0x180006356  cmp     edi, [rbx+8FCh]
0x18000635c  jnz     short loc_180006367
0x18000635e  mov     [rsi+8], rcx
0x180006362  jmp     loc_180006489
0x180006367  cmp     edi, [rbx+900h]
0x18000636d  jnz     short loc_180006378
0x18000636f  mov     [rsi+78h], rcx
0x180006373  jmp     loc_180006489
0x180006378  cmp     edi, [rbx+904h]
0x18000637e  jnz     short loc_18000638C
0x180006380  mov     [rsi+80h], rcx
0x180006387  jmp     loc_180006489
0x18000638c  cmp     edi, [rbx+908h]
0x180006392  jnz     short loc_18000639D
0x180006394  mov     [rsi+10h], rcx
0x180006398  jmp     loc_180006489
0x18000639d  cmp     edi, [rbx+90Ch]
0x1800063a3  jnz     short loc_1800063AE
0x1800063a5  mov     [rsi+18h], rcx
  ... truncated ...
```
