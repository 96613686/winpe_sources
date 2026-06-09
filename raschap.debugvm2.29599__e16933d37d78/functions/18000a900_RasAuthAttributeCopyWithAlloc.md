# RasAuthAttributeCopyWithAlloc

- ea: `0x18000a900`
- end: `0x18000ab29`
- name: `RasAuthAttributeCopyWithAlloc`
- size: `553`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180007370`
- `0x180009c08`
- `0x180009dc0`
- `0x1800122fc`
- `0x180016e2c`

## callees

- `0x18000a900`
- `0x18000ab30`
- `0x18000abc0`
- `0x180025efc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa16`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aab0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aab0`

## pseudocode

```c
char *__fastcall RasAuthAttributeCopyWithAlloc(_DWORD *a1, unsigned int a2)
{
  char *v4; // rdi
  int v6; // eax
  int i; // r15d
  int v8; // r13d
  char *v9; // r14
  const void *v10; // r12
  size_t v11; // rbp
  HLOCAL v12; // rax
  DWORD LastError; // ebp

  if ( a1 )
  {
    v6 = 0;
    if ( *a1 )
    {
      do
        ++v6;
      while ( a1[4 * v6] );
    }
    v4 = (char *)RasAuthAttributeCreate(v6 + a2);
    if ( !v4 )
      return 0;
    for ( i = 0; ; ++i )
    {
      while ( 1 )
      {
        v8 = a1[4 * i];
        if ( !v8 )
          return v4;
        v9 = &v4[16 * i + 16 * a2];
        if ( !*(_DWORD *)v9 )
        {
          LastError = 8;
          goto LABEL_30;
        }
        v10 = *(const void **)&a1[4 * i + 2];
        v11 = (unsigned int)a1[4 * i + 1];
        if ( v8 != 8250 )
          break;
LABEL_17:
        if ( v10 )
        {
          if ( (int)v11 + 1 < (unsigned int)v11 )
          {
            LastError = 534;
LABEL_30:
            RasAuthAttributeDestroy(v4);
            SetLastError(LastError);
            return 0;
          }
          v12 = LocalAlloc(0x40u, (unsigned int)(v11 + 1));
          *((_QWORD *)v9 + 1) = v12;
          if ( v12 )
          {
            memcpy_0(v12, v10, v11);
            ++i;
            *((_DWORD *)v9 + 1) = v11;
            *(_DWORD *)v9 = v8;
          }
          else
          {
            LastError = GetLastError();
            if ( LastError )
              goto LABEL_30;
            ++i;
          }
        }
        else
        {
          *((_QWORD *)v9 + 1) = 0;
          ++i;
          *((_DWORD *)v9 + 1) = v11;
          *(_DWORD *)v9 = v8;
        }
      }
      if ( v8 <= 8097 )
      {
        if ( v8 != 8097 )
        {
          switch ( v8 )
          {
            case 1:
            case 2:
            case 3:
            case 11:
            case 18:
            case 19:
            case 20:
            case 22:
            case 24:
            case 25:
            case 26:
            case 30:
            case 31:
            case 32:
            case 33:
            case 34:
            case 35:
            case 36:
            case 44:
            case 50:
            case 60:
            case 63:
            case 66:
            case 67:
            case 77:
            case 78:
            case 79:
            case 80:
            case 96:
            case 97:
              goto LABEL_17;
            default:
              goto LABEL_25;
          }
        }
        goto LABEL_17;
      }
      if ( v8 > 9000 )
      {
        if ( v8 == 9001 || v8 == 9002 || (unsigned int)(v8 - 9003) < 2 )
          goto LABEL_17;
      }
      else if ( v8 == 9000 || v8 == 8102 )
      {
        goto LABEL_17;
      }
LABEL_25:
      *((_QWORD *)v9 + 1) = v10;
      *((_DWORD *)v9 + 1) = v11;
      *(_DWORD *)v9 = v8;
    }
  }
  v4 = (char *)RasAuthAttributeCreate(a2);
  if ( v4 )
    return v4;
  return 0;
}

```

## disassembly

```asm
0x18000a900  push    rbx
0x18000a902  push    rbp
0x18000a903  push    rsi
0x18000a904  push    rdi
0x18000a905  push    r12
0x18000a907  push    r13
0x18000a909  push    r14
0x18000a90b  push    r15
0x18000a90d  sub     rsp, 28h
0x18000a911  mov     esi, edx
0x18000a913  mov     rbx, rcx
0x18000a916  test    rcx, rcx
0x18000a919  jnz     short loc_18000A942
0x18000a91b  mov     ecx, edx
0x18000a91d  call    RasAuthAttributeCreate
0x18000a922  mov     rdi, rax
0x18000a925  test    rax, rax
0x18000a928  jz      loc_18000AAB6
0x18000a92e  mov     rax, rdi
0x18000a931  add     rsp, 28h
0x18000a935  pop     r15
0x18000a937  pop     r14
0x18000a939  pop     r13
0x18000a93b  pop     r12
0x18000a93d  pop     rdi
0x18000a93e  pop     rsi
0x18000a93f  pop     rbp
0x18000a940  pop     rbx
0x18000a941  retn
0x18000a942  xor     eax, eax
0x18000a944  cmp     [rcx], eax
0x18000a946  jz      short loc_18000A95D
0x18000a948  nop     dword ptr [rax+rax+00000000h]
0x18000a950  inc     eax
0x18000a952  mov     ecx, eax
0x18000a954  add     rcx, rcx
0x18000a957  cmp     dword ptr [rbx+rcx*8], 0
0x18000a95b  jnz     short loc_18000A950
0x18000a95d  lea     ecx, [rax+rdx]
0x18000a960  call    RasAuthAttributeCreate
0x18000a965  mov     rdi, rax
0x18000a968  test    rax, rax
0x18000a96b  jz      loc_18000AAB6
0x18000a971  xor     r15d, r15d
0x18000a974  mov     ebp, r15d
0x18000a977  lea     rdx, __ImageBase
0x18000a97e  add     rbp, rbp
0x18000a981  mov     r13d, [rbx+rbp*8]
0x18000a985  test    r13d, r13d
0x18000a988  jz      short loc_18000A92E
0x18000a98a  lea     r14d, [r15+rsi]
0x18000a98e  shl     r14, 4
0x18000a992  add     r14, rdi
0x18000a995  cmp     dword ptr [r14], 0
0x18000a999  jz      loc_18000AAA1
0x18000a99f  mov     r12, [rbx+rbp*8+8]
0x18000a9a4  mov     ebp, [rbx+rbp*8+4]
0x18000a9a8  cmp     r13d, 203Ah
0x18000a9af  jz      short loc_18000A9FF; jumptable 000000018000A9DD cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000a9b1  cmp     r13d, 1FA1h
0x18000a9b8  jg      short loc_18000A9DF
0x18000a9ba  jz      short loc_18000A9FF; jumptable 000000018000A9DD cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000a9bc  lea     eax, [r13-1]; switch 97 cases
0x18000a9c0  cmp     eax, 60h
0x18000a9c3  ja      def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000a9c9  cdqe
0x18000a9cb  movzx   eax, ds:(byte_18000AAC8 - 180000000h)[rdx+rax]
0x18000a9d3  mov     ecx, ds:(jpt_18000A9DD - 180000000h)[rdx+rax*4]
0x18000a9da  add     rcx, rdx
0x18000a9dd  jmp     rcx; switch jump
0x18000a9df  cmp     r13d, 2328h
0x18000a9e6  jg      short loc_18000AA39
0x18000a9e8  jz      short loc_18000A9FF; jumptable 000000018000A9DD cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000a9ea  mov     ecx, r13d
0x18000a9ed  sub     ecx, 1FA3h
0x18000a9f3  jz      short def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000a9f5  sub     ecx, 1
0x18000a9f8  jz      short def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000a9fa  cmp     ecx, 2
0x18000a9fd  jnz     short def_18000A9DD; jumptable 000000018000A9DD default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000a9ff  test    r12, r12; jumptable 000000018000A9DD cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000aa02  jz      short loc_18000AA83
0x18000aa04  lea     eax, [rbp+1]
0x18000aa07  cmp     eax, ebp
0x18000aa09  jb      loc_18000AA9A
0x18000aa0f  mov     edx, eax; uBytes
0x18000aa11  mov     ecx, 40h ; '@'; uFlags
0x18000aa16  call    cs:__imp_LocalAlloc
0x18000aa1c  mov     [r14+8], rax
0x18000aa20  test    rax, rax
0x18000aa23  jnz     short loc_18000AA66
0x18000aa25  call    cs:__imp_GetLastError
0x18000aa2b  mov     ebp, eax
0x18000aa2d  test    eax, eax
0x18000aa2f  jnz     short loc_18000AAA6
0x18000aa31  inc     r15d
0x18000aa34  jmp     loc_18000A974
0x18000aa39  mov     ecx, r13d
0x18000aa3c  sub     ecx, 2329h
0x18000aa42  jz      short loc_18000A9FF; jumptable 000000018000A9DD cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000aa44  sub     ecx, 1
0x18000aa47  jz      short loc_18000A9FF; jumptable 000000018000A9DD cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000aa49  sub     ecx, 1
0x18000aa4c  jz      short loc_18000A9FF; jumptable 000000018000A9DD cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000aa4e  cmp     ecx, 1
0x18000aa51  jz      short loc_18000A9FF; jumptable 000000018000A9DD cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000aa53  mov     [r14+8], r12; jumptable 000000018000A9DD default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000aa57  inc     r15d
0x18000aa5a  mov     [r14+4], ebp
0x18000aa5e  mov     [r14], r13d
0x18000aa61  jmp     loc_18000A974
0x18000aa66  mov     r8, rbp; Size
0x18000aa69  mov     rdx, r12; Src
0x18000aa6c  mov     rcx, rax; void *
0x18000aa6f  call    memcpy_0
0x18000aa74  inc     r15d
0x18000aa77  mov     [r14+4], ebp
0x18000aa7b  mov     [r14], r13d
0x18000aa7e  jmp     loc_18000A974
0x18000aa83  mov     qword ptr [r14+8], 0
0x18000aa8b  inc     r15d
0x18000aa8e  mov     [r14+4], ebp
0x18000aa92  mov     [r14], r13d
0x18000aa95  jmp     loc_18000A974
0x18000aa9a  mov     ebp, 216h
0x18000aa9f  jmp     short loc_18000AAA6
0x18000aaa1  mov     ebp, 8
0x18000aaa6  mov     rcx, rdi; hMem
0x18000aaa9  call    RasAuthAttributeDestroy
0x18000aaae  mov     ecx, ebp; dwErrCode
0x18000aab0  call    cs:__imp_SetLastError
0x18000aab6  xor     eax, eax
0x18000aab8  jmp     loc_18000A931
```
