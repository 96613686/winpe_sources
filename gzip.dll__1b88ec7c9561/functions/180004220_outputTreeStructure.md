# outputTreeStructure

- ea: `0x180004220`
- end: `0x1800045b0`
- name: `outputTreeStructure`
- size: `912`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180003f30`
- `0x180004760`
- `0x180006038`

## callees

- `0x180003a60`
- `0x180004220`
- `0x180004be0`
- `0x180005688`
- `0x180006ac9`
- `0x180006ad5`
- `0x180006b00`

## pseudocode

```c
__int64 __fastcall outputTreeStructure(__int64 a1, _BYTE *a2, _BYTE *a3)
{
  int i; // edi
  unsigned int v6; // r13d
  int v7; // r12d
  int v8; // edi
  int v9; // r12d
  int v10; // r15d
  int v11; // edx
  __int64 result; // rax
  int j; // ecx
  int k; // edi
  int v15; // r11d
  int v16; // r9d
  __int64 v17; // rcx
  int v18; // r9d
  __int64 v19; // rdx
  int v20; // ecx
  int v21; // r8d
  int v22; // ecx
  int v23; // r9d
  int v24; // r9d
  int v25; // ebx
  __int64 v26; // rcx
  int v27; // r10d
  int v28; // r10d
  int v29; // r9d
  __int16 v30; // cx
  int m; // r9d
  int v32; // r9d
  __int64 v33; // r10
  int v34; // r9d
  int v35; // r10d
  int v36; // r9d
  _BYTE v37[24]; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v38[20]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v39[16]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v40; // [rsp+90h] [rbp-70h]
  __int16 v41; // [rsp+92h] [rbp-6Eh]
  __int16 v42; // [rsp+94h] [rbp-6Ch]
  _BYTE v43[336]; // [rsp+C0h] [rbp-40h] BYREF

  for ( i = 31; i >= 1; --i )
  {
    if ( a3[i] )
      break;
  }
  v6 = i;
  v7 = 287;
  v8 = i + 1;
  do
  {
    if ( a2[v7] )
      break;
    --v7;
  }
  while ( v7 >= 257 );
  v9 = v7 + 1;
  v10 = v9 + v8;
  memcpy_0(v43, a2, v9);
  memcpy_0(&v43[v9], a3, v8);
  result = 323;
  if ( (unsigned __int64)(v9 + v8) < 0x143 )
  {
    LOBYTE(v11) = -1;
    result = (__int64)memset_0(&v43[v10], v11, 323 - v10);
  }
  for ( j = 0; j < 19; ++j )
  {
    if ( (unsigned __int64)(2LL * j) >= 0x4C )
      _report_rangecheckfailure();
    result = 0;
    v39[j] = 0;
  }
  for ( k = 0; k < 2; ++k )
  {
    while ( 1 )
    {
      v15 = 0;
      while ( v15 < v10 )
      {
        result = v15;
        v16 = v15 + 1;
        v17 = (unsigned __int8)v43[v15];
        if ( v43[v15 + 1] == (_BYTE)v17 )
        {
          do
            result = ++v16;
          while ( v43[v16] == (_BYTE)v17 );
        }
        v18 = v16 - v15;
        if ( (_BYTE)v17 )
          --v18;
        if ( v18 >= 3 )
        {
          if ( (_BYTE)v17 )
          {
            v25 = 0;
            v26 = v17;
            if ( k == 1 )
            {
              outputBits(a1, (unsigned __int8)v37[(unsigned __int8)v43[v15]], (unsigned __int16)v38[v26]);
              do
              {
                outputBits(a1, v37[16], v38[16]);
                result = outputBits(a1, 2, (unsigned int)(v27 - 3));
                v25 += v28;
              }
              while ( v29 - v28 >= 3 );
            }
            else
            {
              ++v39[v26];
              v30 = v40;
              do
              {
                result = 6;
                if ( (unsigned int)v18 <= 6 )
                  result = (unsigned int)v18;
                ++v30;
                v25 += result;
                v18 -= result;
              }
              while ( v18 >= 3 );
              v40 = v30;
            }
            v15 += v25 + 1;
          }
          else
          {
            if ( v18 > 10 )
            {
              if ( v18 > 138 )
                v18 = 138;
              if ( k == 1 )
              {
                outputBits(a1, v37[18], v38[18]);
                result = outputBits(a1, 7, (unsigned int)(v24 - 11));
              }
              else
              {
                ++v42;
              }
            }
            else if ( k == 1 )
            {
              outputBits(a1, v37[17], v38[17]);
              result = outputBits(a1, 3, (unsigned int)(v23 - 3));
            }
            else
            {
              ++v41;
            }
            v15 += v18;
          }
        }
        else
        {
          ++v15;
          v19 = v17;
          if ( k == 1 )
          {
            v20 = *(_DWORD *)(a1 + 68);
            *(_DWORD *)(a1 + 64) |= (unsigned __int16)v38[v19] << v20;
            result = (unsigned __int8)v37[v19];
            v21 = *(_DWORD *)(a1 + 64);
            v22 = result + v20;
            *(_DWORD *)(a1 + 68) = v22;
            if ( v22 >= 16 )
            {
              *(_BYTE *)(*(_QWORD *)(a1 + 40))++ = v21;
              *(_BYTE *)(*(_QWORD *)(a1 + 40))++ = BYTE1(*(_DWORD *)(a1 + 64));
              result = *(unsigned __int16 *)(a1 + 66);
              *(_DWORD *)(a1 + 68) -= 16;
              *(_DWORD *)(a1 + 64) = result;
            }
          }
          else
          {
            ++v39[v17];
          }
        }
      }
      if ( k )
        break;
      makeTree(19, 7, v39, v38, (__int64)v37);
      for ( m = 18; m >= 4; --m )
      {
        if ( v37[*((unsigned __int8 *)g_CodeOrder + (unsigned int)m)] )
          break;
      }
      outputBits(a1, 5, (unsigned int)(v9 - 257));
      outputBits(a1, 5, v6);
      result = outputBits(a1, 4, (unsigned int)(v32 - 4));
      v33 = 0;
      if ( v34 <= 0 )
        break;
      do
      {
        result = outputBits(a1, 3, (unsigned __int8)v37[*((unsigned __int8 *)g_CodeOrder + v33)]);
        v33 = (unsigned int)(v35 + 1);
      }
      while ( (int)v33 < v36 );
      k = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004220  mov     [rsp-8+arg_18], rbx
0x180004225  push    rbp
0x180004226  push    rsi
0x180004227  push    rdi
0x180004228  push    r12
0x18000422a  push    r13
0x18000422c  push    r14
0x18000422e  push    r15
0x180004230  lea     rbp, [rsp-120h]
0x180004238  sub     rsp, 220h
0x18000423f  mov     rax, cs:__security_cookie
0x180004246  xor     rax, rsp
0x180004249  mov     [rbp+150h+var_40], rax
0x180004250  mov     r14, r8
0x180004253  mov     rsi, rcx
0x180004256  mov     edi, 1Fh
0x18000425b  mov     eax, edi
0x18000425d  cmp     byte ptr [rax+r8], 0
0x180004262  jnz     short loc_18000426B
0x180004264  dec     edi
0x180004266  cmp     edi, 1
0x180004269  jge     short loc_18000425B
0x18000426b  mov     r13d, edi
0x18000426e  mov     r12d, 11Fh
0x180004274  inc     edi
0x180004276  mov     eax, r12d
0x180004279  cmp     byte ptr [rax+rdx], 0
0x18000427d  jnz     short loc_18000428B
0x18000427f  dec     r12d
0x180004282  cmp     r12d, 101h
0x180004289  jge     short loc_180004276
0x18000428b  inc     r12d
0x18000428e  lea     rcx, [rbp+150h+var_190]; void *
0x180004292  movsxd  rbx, r12d
0x180004295  mov     r8, rbx; Size
0x180004298  lea     r15d, [r12+rdi]
0x18000429c  call    memcpy_0
0x1800042a1  lea     rcx, [rbp+150h+var_190]
0x1800042a5  movsxd  r8, edi; Size
0x1800042a8  add     rcx, rbx; void *
0x1800042ab  mov     rdx, r14; Src
0x1800042ae  call    memcpy_0
0x1800042b3  movsxd  rcx, r15d
0x1800042b6  mov     eax, 143h
0x1800042bb  cmp     rcx, rax
0x1800042be  jnb     short loc_1800042D4
0x1800042c0  sub     eax, r15d
0x1800042c3  mov     dl, 0FFh; Val
0x1800042c5  movsxd  r8, eax; Size
0x1800042c8  lea     rax, [rbp+150h+var_190]
0x1800042cc  add     rcx, rax; void *
0x1800042cf  call    memset_0
0x1800042d4  xor     ecx, ecx
0x1800042d6  cmp     ecx, 13h
0x1800042d9  jge     short loc_1800042F9
0x1800042db  movsxd  rax, ecx
0x1800042de  lea     rdx, [rax+rax]
0x1800042e2  cmp     rdx, 4Ch ; 'L'
0x1800042e6  jnb     short loc_1800042F3
0x1800042e8  xor     eax, eax
0x1800042ea  mov     [rsp+rdx+250h+var_1E0], ax
0x1800042ef  inc     ecx
0x1800042f1  jmp     short loc_1800042D6
0x1800042f3  call    __report_rangecheckfailure
0x1800042f9  xor     edi, edi
0x1800042fb  lea     rbx, g_CodeOrder
0x180004302  mov     r14d, 8Ah
0x180004308  xor     r11d, r11d
0x18000430b  test    r15d, r15d
0x18000430e  jle     loc_1800044CB
0x180004314  nop     dword ptr [rax+00h]
0x180004318  nop     dword ptr [rax+rax+00000000h]
0x180004320  movsxd  rax, r11d
0x180004323  lea     edx, [r11+1]
0x180004327  movsxd  r9, edx
0x18000432a  movzx   ecx, [rbp+rax+150h+var_190]
0x18000432f  cmp     [rbp+r9+150h+var_190], cl
0x180004334  jnz     short loc_180004342
0x180004336  inc     r9d
0x180004339  movsxd  rax, r9d
0x18000433c  cmp     [rbp+rax+150h+var_190], cl
0x180004340  jz      short loc_180004336
0x180004342  sub     r9d, r11d
0x180004345  test    cl, cl
0x180004347  jz      short loc_18000434C
0x180004349  dec     r9d
0x18000434c  cmp     r9d, 3
0x180004350  jge     short loc_1800043B6
0x180004352  mov     r11d, edx
0x180004355  mov     rdx, rcx
0x180004358  cmp     edi, 1
0x18000435b  jnz     short loc_1800043AC
0x18000435d  mov     ecx, [rsi+44h]
0x180004360  movzx   eax, [rsp+rdx*2+250h+var_208]
0x180004365  shl     eax, cl
0x180004367  or      [rsi+40h], eax
0x18000436a  movzx   eax, [rsp+rdx+250h+var_220]
0x18000436f  mov     r8d, [rsi+40h]
0x180004373  add     ecx, eax
0x180004375  mov     [rsi+44h], ecx
0x180004378  cmp     ecx, 10h
0x18000437b  jl      loc_1800044BB
0x180004381  mov     rax, [rsi+28h]
0x180004385  mov     [rax], r8b
0x180004388  inc     qword ptr [rsi+28h]
0x18000438c  mov     eax, [rsi+40h]
0x18000438f  mov     rcx, [rsi+28h]
0x180004393  shr     eax, 8
0x180004396  mov     [rcx], al
0x180004398  inc     qword ptr [rsi+28h]
0x18000439c  movzx   eax, word ptr [rsi+42h]
0x1800043a0  add     dword ptr [rsi+44h], 0FFFFFFF0h
0x1800043a4  mov     [rsi+40h], eax
0x1800043a7  jmp     loc_1800044BB
0x1800043ac  inc     [rsp+rcx*2+250h+var_1E0]
0x1800043b1  jmp     loc_1800044BB
0x1800043b6  test    cl, cl
0x1800043b8  jnz     short loc_18000442F
0x1800043ba  cmp     r9d, 0Ah
0x1800043be  jg      short loc_1800043F1
0x1800043c0  cmp     edi, 1
0x1800043c3  jnz     short loc_1800043EB
0x1800043c5  movzx   r8d, [rsp+250h+var_1E6]
0x1800043cb  mov     rcx, rsi
0x1800043ce  movzx   edx, [rsp+250h+var_20F]
0x1800043d3  call    outputBits
0x1800043d8  lea     r8d, [r9-3]
0x1800043dc  mov     edx, 3
0x1800043e1  mov     rcx, rsi
0x1800043e4  call    outputBits
0x1800043e9  jmp     short loc_180004427
0x1800043eb  inc     [rbp+150h+var_1BE]
0x1800043ef  jmp     short loc_180004427
0x1800043f1  cmp     r9d, r14d
0x1800043f4  cmovg   r9d, r14d
0x1800043f8  cmp     edi, 1
0x1800043fb  jnz     short loc_180004423
0x1800043fd  movzx   r8d, [rsp+250h+var_1E4]
0x180004403  mov     rcx, rsi
0x180004406  movzx   edx, [rsp+250h+var_20E]
0x18000440b  call    outputBits
0x180004410  lea     r8d, [r9-0Bh]
0x180004414  mov     edx, 7
0x180004419  mov     rcx, rsi
0x18000441c  call    outputBits
0x180004421  jmp     short loc_180004427
0x180004423  inc     [rbp+150h+var_1BC]
0x180004427  add     r11d, r9d
0x18000442a  jmp     loc_1800044BB
0x18000442f  mov     rax, rcx
0x180004432  xor     ebx, ebx
0x180004434  add     rcx, rcx
0x180004437  cmp     edi, 1
0x18000443a  jnz     short loc_18000448E
0x18000443c  movzx   r8d, [rsp+rcx+250h+var_208]
0x180004442  mov     rcx, rsi
0x180004445  movzx   edx, [rsp+rax+250h+var_220]
0x18000444a  call    outputBits
0x18000444f  movzx   r8d, [rsp+250h+var_1E8]
0x180004455  mov     r10d, 6
0x18000445b  movzx   edx, [rsp+250h+var_210]
0x180004460  cmp     r9d, r10d
0x180004463  mov     rcx, rsi
0x180004466  cmovbe  r10d, r9d
0x18000446a  call    outputBits
0x18000446f  lea     r8d, [r10-3]
0x180004473  mov     edx, 2
0x180004478  mov     rcx, rsi
0x18000447b  call    outputBits
0x180004480  add     ebx, r10d
0x180004483  sub     r9d, r10d
0x180004486  cmp     r9d, 3
0x18000448a  jge     short loc_18000444F
0x18000448c  jmp     short loc_1800044B5
0x18000448e  inc     [rsp+rcx+250h+var_1E0]
0x180004493  movzx   ecx, [rbp+150h+var_1C0]
0x180004497  mov     eax, 6
0x18000449c  cmp     r9d, eax
0x18000449f  cmovbe  eax, r9d
0x1800044a3  inc     cx
0x1800044a6  add     ebx, eax
0x1800044a8  sub     r9d, eax
0x1800044ab  cmp     r9d, 3
0x1800044af  jge     short loc_180004497
0x1800044b1  mov     [rbp+150h+var_1C0], cx
0x1800044b5  inc     r11d
0x1800044b8  add     r11d, ebx
0x1800044bb  cmp     r11d, r15d
0x1800044be  jl      loc_180004320
0x1800044c4  lea     rbx, g_CodeOrder
0x1800044cb  test    edi, edi
0x1800044cd  jnz     loc_18000457B
0x1800044d3  lea     rax, [rsp+250h+var_220]
0x1800044d8  mov     edx, 7
0x1800044dd  lea     r9, [rsp+250h+var_208]
0x1800044e2  mov     [rsp+250h+var_230], rax
0x1800044e7  lea     r8, [rsp+250h+var_1E0]
0x1800044ec  mov     ecx, 13h
0x1800044f1  call    makeTree
0x1800044f6  mov     r9d, 12h
0x1800044fc  mov     eax, r9d
0x1800044ff  movzx   eax, byte ptr [rax+rbx]
0x180004503  cmp     [rsp+rax+250h+var_220], 0
0x180004508  jnz     short loc_180004513
0x18000450a  dec     r9d
0x18000450d  cmp     r9d, 4
0x180004511  jge     short loc_1800044FC
0x180004513  lea     r8d, [r12-101h]
0x18000451b  mov     edx, 5
0x180004520  mov     rcx, rsi
0x180004523  inc     r9d
0x180004526  call    outputBits
0x18000452b  mov     r8d, r13d
0x18000452e  mov     edx, 5
0x180004533  mov     rcx, rsi
0x180004536  call    outputBits
0x18000453b  lea     r8d, [r9-4]
0x18000453f  mov     edx, 4
0x180004544  mov     rcx, rsi
0x180004547  call    outputBits
0x18000454c  xor     r10d, r10d
0x18000454f  test    r9d, r9d
0x180004552  jle     short loc_18000457B
0x180004554  movzx   eax, byte ptr [r10+rbx]
0x180004559  mov     edx, 3
0x18000455e  mov     rcx, rsi
0x180004561  movzx   r8d, [rsp+rax+250h+var_220]
0x180004567  call    outputBits
0x18000456c  inc     r10d
0x18000456f  cmp     r10d, r9d
0x180004572  jl      short loc_180004554
0x180004574  inc     edi
0x180004576  jmp     loc_180004308
0x18000457b  inc     edi
0x18000457d  cmp     edi, 2
0x180004580  jl      loc_180004308
0x180004586  mov     rcx, [rbp+150h+var_40]
0x18000458d  xor     rcx, rsp; StackCookie
0x180004590  call    __security_check_cookie
0x180004595  mov     rbx, [rsp+250h+arg_18]
0x18000459d  add     rsp, 220h
0x1800045a4  pop     r15
0x1800045a6  pop     r14
0x1800045a8  pop     r13
0x1800045aa  pop     r12
0x1800045ac  pop     rdi
0x1800045ad  pop     rsi
0x1800045ae  pop     rbp
0x1800045af  retn
```
