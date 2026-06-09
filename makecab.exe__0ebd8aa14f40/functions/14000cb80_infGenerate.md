# infGenerate

- ea: `0x14000cb80`
- end: `0x14000cde5`
- name: `infGenerate`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140003f68`

## callees

- `0x140001508`
- `0x140008620`
- `0x140008ee4`
- `0x14000acd8`
- `0x14000b128`
- `0x14000cb80`
- `0x14000dfd8`
- `0x14000e450`

## import_xrefs

- `msvcrt!ctime` at `0x14000cc44`
- `msvcrt!ctime` at `0x14000cc44`
- `msvcrt!fclose` at `0x14000cd9c`
- `msvcrt!fclose` at `0x14000cdac`
- `msvcrt!fclose` at `0x14000cd9c`
- `msvcrt!fclose` at `0x14000cdac`
- `msvcrt!fopen` at `0x14000cbed`
- `msvcrt!fopen` at `0x14000cbed`
- `msvcrt!toupper` at `0x14000cd13`
- `msvcrt!toupper` at `0x14000cd13`

## string_xrefs

- `0x14000cc1d`: `InfCommentString`
- `0x14000cc05`: `Cannot create INF file: %1`

## pseudocode

```c
__int64 __fastcall infGenerate(__int64 a1, const char *a2, const time_t *a3, __int64 a4, __int64 a5)
{
  __int64 v6; // r12
  __int64 v9; // rbx
  __int64 v10; // rcx
  FILE *v11; // rdi
  __int64 v12; // rax
  const char *v13; // r15
  __int64 v14; // rbx
  char *v15; // rax
  __int64 v16; // rcx
  _BYTE *v17; // rdx
  _BYTE *v18; // rax
  __int64 v19; // rax
  unsigned __int64 v20; // rax
  __int64 v21; // rax
  const char *v22; // rbx
  int v23; // eax
  __int64 v24; // r9
  __int64 v25; // r8
  _BYTE v27[56]; // [rsp+50h] [rbp-78h] BYREF

  v6 = *(_QWORD *)(a1 + 144);
  v9 = 0;
  while ( 1 )
  {
    v10 = *(_QWORD *)(v6 + 8 * v9);
    if ( v10 )
    {
      if ( !(unsigned int)TmpClose(v10, a5) )
        return 0;
    }
    v9 = (unsigned int)(v9 + 1);
    if ( (int)v9 >= 3 )
    {
      v11 = fopen(a2, "wb");
      if ( v11 )
      {
        v12 = VarFind(*(_QWORD *)(a1 + 16), "InfCommentString", a5);
        v13 = ";";
        if ( v12 )
          v13 = *(const char **)(v12 + 8);
        v14 = 2147483646;
        v15 = ctime(a3);
        v16 = 50;
        v17 = v27;
        do
        {
          if ( !v14 )
            break;
          if ( !*v15 )
            break;
          *v17++ = *v15++;
          --v14;
          --v16;
        }
        while ( v16 );
        v18 = v17 - 1;
        if ( v16 )
          v18 = v17;
        *v18 = 0;
        if ( v16 )
        {
          v19 = -1;
          do
            ++v19;
          while ( v27[v19] );
          v20 = v19 - 1;
          if ( v20 >= 0x32 )
            _report_rangecheckfailure(v27);
          v27[v20] = 0;
          if ( (unsigned int)doHeaderFooter(a1, v11, a2, "InfHeader", "InfHeader*", v13, v27) )
          {
            v21 = VarFind(*(_QWORD *)(a1 + 16), "InfSectionOrder", a5);
            v22 = "DCF";
            if ( v21 )
              v22 = *(const char **)(v21 + 8);
            while ( *v22 )
            {
              v23 = toupper(*v22);
              switch ( v23 )
              {
                case 'C':
                  v25 = 8;
                  break;
                case 'D':
                  v25 = 0;
                  break;
                case 'F':
                  v25 = 16;
                  break;
                default:
                  return 0;
              }
              if ( !(unsigned int)catTempFile(v11, a2, *(FILE ***)(v25 + v6), v24, a5) )
                goto LABEL_33;
              ++v22;
            }
            if ( (unsigned int)doHeaderFooter(a1, v11, a2, "InfFooter", "InfFooter*", v13, v27) )
            {
              fclose(v11);
              return 1;
            }
          }
        }
LABEL_33:
        fclose(v11);
      }
      else
      {
        ErrSet(a5, "Cannot create INF file: %1", "%s", a2);
      }
      return 0;
    }
  }
}

```

## disassembly

```asm
0x14000cb80  mov     [rsp+arg_18], rbx
0x14000cb85  push    rbp
0x14000cb86  push    rsi
0x14000cb87  push    rdi
0x14000cb88  push    r12
0x14000cb8a  push    r13
0x14000cb8c  push    r14
0x14000cb8e  push    r15
0x14000cb90  sub     rsp, 90h
0x14000cb97  mov     rax, cs:__security_cookie
0x14000cb9e  xor     rax, rsp
0x14000cba1  mov     [rsp+0C8h+var_40], rax
0x14000cba9  mov     rsi, [rsp+0C8h+arg_20]
0x14000cbb1  mov     r14, r8
0x14000cbb4  mov     r12, [rcx+90h]
0x14000cbbb  mov     rbp, rdx
0x14000cbbe  mov     r13, rcx
0x14000cbc1  xor     ebx, ebx
0x14000cbc3  mov     rcx, [r12+rbx*8]
0x14000cbc7  test    rcx, rcx
0x14000cbca  jz      short loc_14000CBDC
0x14000cbcc  mov     rdx, rsi
0x14000cbcf  call    TmpClose
0x14000cbd4  test    eax, eax
0x14000cbd6  jz      loc_14000CDB2
0x14000cbdc  inc     ebx
0x14000cbde  cmp     ebx, 3
0x14000cbe1  jl      short loc_14000CBC3
0x14000cbe3  lea     rdx, aWb; "wb"
0x14000cbea  mov     rcx, rbp; FileName
0x14000cbed  call    cs:__imp_fopen
0x14000cbf3  mov     rdi, rax
0x14000cbf6  test    rax, rax
0x14000cbf9  jnz     short loc_14000CC19
0x14000cbfb  mov     r9, rbp
0x14000cbfe  lea     r8, aS_4; "%s"
0x14000cc05  lea     rdx, aCannotCreateIn; "Cannot create INF file: %1"
0x14000cc0c  mov     rcx, rsi
0x14000cc0f  call    ErrSet
0x14000cc14  jmp     loc_14000CDB2
0x14000cc19  mov     rcx, [r13+10h]
0x14000cc1d  lea     rdx, aInfcommentstri; "InfCommentString"
0x14000cc24  mov     r8, rsi
0x14000cc27  call    VarFind
0x14000cc2c  lea     r15, asc_140011714; ";"
0x14000cc33  test    rax, rax
0x14000cc36  jz      short loc_14000CC3C
0x14000cc38  mov     r15, [rax+8]
0x14000cc3c  mov     rcx, r14; Time
0x14000cc3f  mov     ebx, 7FFFFFFEh
0x14000cc44  call    cs:__imp_ctime
0x14000cc4a  mov     ecx, 32h ; '2'
0x14000cc4f  lea     rdx, [rsp+0C8h+var_78]
0x14000cc54  xor     r14d, r14d
0x14000cc57  test    rbx, rbx
0x14000cc5a  jz      short loc_14000CC76
0x14000cc5c  mov     r8b, [rax]
0x14000cc5f  test    r8b, r8b
0x14000cc62  jz      short loc_14000CC76
0x14000cc64  mov     [rdx], r8b
0x14000cc67  inc     rax
0x14000cc6a  inc     rdx
0x14000cc6d  dec     rbx
0x14000cc70  sub     rcx, 1
0x14000cc74  jnz     short loc_14000CC57
0x14000cc76  test    rcx, rcx
0x14000cc79  lea     rax, [rdx-1]
0x14000cc7d  cmovnz  rax, rdx
0x14000cc81  mov     [rax], r14b
0x14000cc84  jz      loc_14000CDA9
0x14000cc8a  lea     rcx, [rsp+0C8h+var_78]
0x14000cc8f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000cc93  inc     rax
0x14000cc96  cmp     [rcx+rax], r14b
0x14000cc9a  jnz     short loc_14000CC93
0x14000cc9c  dec     rax
0x14000cc9f  cmp     rax, 32h ; '2'
0x14000cca3  jnb     loc_14000CDDF
0x14000cca9  mov     [rsp+rax+0C8h+var_78], r14b
0x14000ccae  lea     r9, aInfheader; "InfHeader"
0x14000ccb5  mov     [rsp+0C8h+var_88], rsi
0x14000ccba  lea     rax, [rsp+0C8h+var_78]
0x14000ccbf  mov     [rsp+0C8h+var_98], rax
0x14000ccc4  mov     r8, rbp
0x14000ccc7  lea     rax, aInfheader_0; "InfHeader*"
0x14000ccce  mov     [rsp+0C8h+var_A0], r15
0x14000ccd3  mov     rdx, rdi
0x14000ccd6  mov     [rsp+0C8h+var_A8], rax
0x14000ccdb  mov     rcx, r13
0x14000ccde  call    doHeaderFooter
0x14000cce3  test    eax, eax
0x14000cce5  jz      loc_14000CDA9
0x14000cceb  mov     rcx, [r13+10h]
0x14000ccef  lea     rdx, aInfsectionorde; "InfSectionOrder"
0x14000ccf6  mov     r8, rsi
0x14000ccf9  call    VarFind
0x14000ccfe  lea     rbx, aDcf; "DCF"
0x14000cd05  test    rax, rax
0x14000cd08  jz      short loc_14000CD5A
0x14000cd0a  mov     rbx, [rax+8]
0x14000cd0e  jmp     short loc_14000CD5A
0x14000cd10  movsx   ecx, al; C
0x14000cd13  call    cs:__imp_toupper
0x14000cd19  mov     ecx, eax
0x14000cd1b  sub     ecx, 43h ; 'C'
0x14000cd1e  jz      short loc_14000CD39
0x14000cd20  sub     ecx, 1
0x14000cd23  jz      short loc_14000CD34
0x14000cd25  cmp     ecx, 2
0x14000cd28  jnz     loc_14000CDB2
0x14000cd2e  lea     r8d, [rcx+0Eh]
0x14000cd32  jmp     short loc_14000CD3F
0x14000cd34  mov     r8, r14
0x14000cd37  jmp     short loc_14000CD3F
0x14000cd39  mov     r8d, 8
0x14000cd3f  mov     r8, [r8+r12]
0x14000cd43  mov     rdx, rbp
0x14000cd46  mov     rcx, rdi
0x14000cd49  mov     [rsp+0C8h+var_A8], rsi
0x14000cd4e  call    catTempFile
0x14000cd53  test    eax, eax
0x14000cd55  jz      short loc_14000CDA9
0x14000cd57  inc     rbx
0x14000cd5a  mov     al, [rbx]
0x14000cd5c  test    al, al
0x14000cd5e  jnz     short loc_14000CD10
0x14000cd60  mov     [rsp+0C8h+var_88], rsi
0x14000cd65  lea     rax, [rsp+0C8h+var_78]
0x14000cd6a  mov     [rsp+0C8h+var_98], rax
0x14000cd6f  lea     rcx, aInffooter; "InfFooter*"
0x14000cd76  mov     [rsp+0C8h+var_A0], r15
0x14000cd7b  lea     r9, aInffooter_0; "InfFooter"
0x14000cd82  mov     [rsp+0C8h+var_A8], rcx
0x14000cd87  mov     r8, rbp
0x14000cd8a  mov     rcx, r13
0x14000cd8d  mov     rdx, rdi
0x14000cd90  call    doHeaderFooter
0x14000cd95  test    eax, eax
0x14000cd97  jz      short loc_14000CDA9
0x14000cd99  mov     rcx, rdi; Stream
0x14000cd9c  call    cs:__imp_fclose
0x14000cda2  mov     eax, 1
0x14000cda7  jmp     short loc_14000CDB4
0x14000cda9  mov     rcx, rdi; Stream
0x14000cdac  call    cs:__imp_fclose
0x14000cdb2  xor     eax, eax
0x14000cdb4  mov     rcx, [rsp+0C8h+var_40]
0x14000cdbc  xor     rcx, rsp; StackCookie
0x14000cdbf  call    __security_check_cookie
0x14000cdc4  mov     rbx, [rsp+0C8h+arg_18]
0x14000cdcc  add     rsp, 90h
0x14000cdd3  pop     r15
0x14000cdd5  pop     r14
0x14000cdd7  pop     r13
0x14000cdd9  pop     r12
0x14000cddb  pop     rdi
0x14000cddc  pop     rsi
0x14000cddd  pop     rbp
0x14000cdde  retn
0x14000cddf  call    __report_rangecheckfailure
```
