# JsonReader::DecodeString(unsigned __int64,ulong,ulong)

- ea: `0x140023578`
- end: `0x14002383b`
- name: `?DecodeString@JsonReader@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KKK@Z`
- size: `707`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1400244d4`

## callees

- `0x1400028ac`
- `0x140003044`
- `0x14001c78c`
- `0x140023578`
- `0x14002c3e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400235b5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400235b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall JsonReader::DecodeString(__int64 a1, _QWORD *a2, __int64 a3, unsigned int a4, unsigned int a5)
{
  __int64 v5; // rdi
  __int64 v9; // r12
  _WORD *v10; // rbx
  unsigned __int64 v11; // r9
  unsigned __int64 v12; // rsi
  __int64 v13; // r10
  __int16 v14; // cx
  int i; // r8d
  __int16 v16; // dx
  __int16 v17; // cx
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-18h] BYREF

  LODWORD(v5) = a4;
  if ( !a3 || a4 > a5 )
  {
    JsonException::JsonException((JsonException *)pExceptionObject, -895090685);
    throw (JsonException *)pExceptionObject;
  }
  v9 = a3;
  v10 = malloc(2 * a3);
  if ( !v10 )
  {
    JsonException::JsonException((JsonException *)pExceptionObject, -895090686);
    throw (JsonException *)pExceptionObject;
  }
  v11 = 0;
  v12 = a3 - 1;
  if ( v12 )
  {
    do
    {
      if ( (unsigned int)v5 > a5 )
        break;
      v13 = *(_QWORD *)(a1 + 40);
      v14 = *(_WORD *)(v13 + 2LL * (unsigned int)v5);
      if ( v14 == 92 )
      {
        v5 = (unsigned int)(v5 + 1);
        if ( (unsigned int)v5 > a5 )
        {
          JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
          throw (JsonException *)pExceptionObject;
        }
        switch ( *(_WORD *)(v13 + 2 * v5) )
        {
          case '"':
            v14 = 34;
            break;
          case '/':
            v14 = 47;
            break;
          case '\\':
            v14 = 92;
            break;
          case 'b':
            v14 = 8;
            break;
          case 'f':
            v14 = 12;
            break;
          case 'n':
            v14 = 10;
            break;
          case 'r':
            v14 = 13;
            break;
          case 't':
            v14 = 9;
            break;
          case 'u':
            if ( a5 < (int)v5 + 4 )
            {
              JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
              throw (JsonException *)pExceptionObject;
            }
            v14 = 0;
            for ( i = 0; i < 4; ++i )
            {
              v5 = (unsigned int)(v5 + 1);
              v16 = *(_WORD *)(v13 + 2 * v5);
              if ( (unsigned __int16)(v16 - 48) > 9u )
              {
                if ( (unsigned __int16)(v16 - 97) > 5u )
                {
                  if ( (unsigned __int16)(v16 - 65) > 5u )
                  {
                    JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
                    throw (JsonException *)pExceptionObject;
                  }
                  v17 = 16 * v14 - 55;
                }
                else
                {
                  v17 = 16 * v14 - 87;
                }
              }
              else
              {
                v17 = 16 * (v14 - 3);
              }
              v14 = v16 + v17;
            }
            break;
          default:
            JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
            throw (JsonException *)pExceptionObject;
        }
      }
      v10[v11++] = v14;
      LODWORD(v5) = v5 + 1;
    }
    while ( v11 < v12 );
  }
  v10[v9 - 1] = 0;
  if ( v11 != v12 || (_DWORD)v5 != a5 + 1 )
  {
    JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
    throw (JsonException *)pExceptionObject;
  }
  std::wstring::wstring(a2, v10);
  operator delete(v10);
  return a2;
}

```

## disassembly

```asm
0x140023578  push    rbp
0x14002357a  push    rbx
0x14002357b  push    rsi
0x14002357c  push    rdi
0x14002357d  push    r12
0x14002357f  push    r13
0x140023581  push    r14
0x140023583  push    r15
0x140023585  mov     rbp, rsp
0x140023588  sub     rsp, 48h
0x14002358c  mov     edi, r9d
0x14002358f  mov     rsi, r8
0x140023592  mov     r15, rdx
0x140023595  mov     r13, rcx
0x140023598  test    r8, r8
0x14002359b  jz      loc_140023781
0x1400235a1  mov     r14d, [rbp+arg_20]
0x1400235a5  cmp     r9d, r14d
0x1400235a8  ja      loc_140023781
0x1400235ae  lea     r12, [r8+r8]
0x1400235b2  mov     rcx, r12; Size
0x1400235b5  call    cs:__imp_malloc
0x1400235bb  mov     rbx, rax
0x1400235be  mov     [rbp+var_20], rax
0x1400235c2  test    rax, rax
0x1400235c5  jz      loc_140023762
0x1400235cb  xor     r9d, r9d
0x1400235ce  sub     rsi, 1
0x1400235d2  jz      loc_140023713
0x1400235d8  lea     r8d, [r9+5Ch]
0x1400235dc  lea     r11d, [r9+0Dh]
0x1400235e0  mov     [rbp+arg_10], 9
0x1400235e7  mov     edx, 8
0x1400235ec  cmp     edi, r14d
0x1400235ef  ja      loc_140023713
0x1400235f5  mov     r10, [r13+28h]
0x1400235f9  mov     eax, edi
0x1400235fb  movzx   ecx, word ptr [r10+rax*2]
0x140023600  cmp     cx, r8w
0x140023604  jnz     loc_1400236FB
0x14002360a  inc     edi
0x14002360c  cmp     edi, r14d
0x14002360f  ja      loc_1400237FD
0x140023615  movzx   ecx, word ptr [r10+rdi*2]
0x14002361a  lea     eax, [rdx+1Ah]
0x14002361d  sub     ecx, eax
0x14002361f  jz      loc_1400236F8
0x140023625  sub     ecx, r11d
0x140023628  jz      loc_1400236F1
0x14002362e  sub     ecx, 2Dh ; '-'
0x140023631  jz      loc_1400236EB
0x140023637  sub     ecx, 6
0x14002363a  jz      loc_1400236E6
0x140023640  sub     ecx, 4
0x140023643  jz      loc_1400236DF
0x140023649  sub     ecx, edx
0x14002364b  jz      loc_1400236D8
0x140023651  sub     ecx, 4
0x140023654  jz      short loc_1400236D2
0x140023656  sub     ecx, 2
0x140023659  jz      short loc_1400236CB
0x14002365b  cmp     ecx, 1
0x14002365e  jnz     loc_1400237DE
0x140023664  lea     eax, [rdi+4]
0x140023667  cmp     r14d, eax
0x14002366a  jb      loc_1400237BF
0x140023670  xor     ecx, ecx
0x140023672  xor     r8d, r8d
0x140023675  inc     edi
0x140023677  movzx   edx, word ptr [r10+rdi*2]
0x14002367c  lea     eax, [rdx-30h]
0x14002367f  cmp     ax, word ptr [rbp+arg_10]
0x140023683  ja      short loc_14002368F
0x140023685  sub     cx, 3
0x140023689  shl     cx, 4
0x14002368d  jmp     short loc_1400236B7
0x14002368f  lea     eax, [rdx-61h]
0x140023692  cmp     ax, 5
0x140023696  ja      short loc_1400236A2
0x140023698  shl     cx, 4
0x14002369c  sub     cx, 57h ; 'W'
0x1400236a0  jmp     short loc_1400236B7
0x1400236a2  lea     eax, [rdx-41h]
0x1400236a5  cmp     ax, 5
0x1400236a9  ja      loc_1400237A0
0x1400236af  shl     cx, 4
0x1400236b3  sub     cx, 37h ; '7'
0x1400236b7  add     cx, dx
0x1400236ba  inc     r8d
0x1400236bd  cmp     r8d, 4
0x1400236c1  jl      short loc_140023675
0x1400236c3  mov     r8d, 5Ch ; '\'
0x1400236c9  jmp     short loc_1400236FB
0x1400236cb  mov     ecx, 9
0x1400236d0  jmp     short loc_1400236FB
0x1400236d2  movzx   ecx, r11w
0x1400236d6  jmp     short loc_1400236FB
0x1400236d8  mov     ecx, 0Ah
0x1400236dd  jmp     short loc_1400236FB
0x1400236df  mov     ecx, 0Ch
0x1400236e4  jmp     short loc_1400236FB
0x1400236e6  movzx   ecx, dx
0x1400236e9  jmp     short loc_1400236FB
0x1400236eb  movzx   ecx, r8w
0x1400236ef  jmp     short loc_1400236FB
0x1400236f1  mov     ecx, 2Fh ; '/'
0x1400236f6  jmp     short loc_1400236FB
0x1400236f8  movzx   ecx, ax
0x1400236fb  mov     rdx, r9
0x1400236fe  mov     rax, rbx
0x140023701  mov     [rbx+rdx*2], cx
0x140023705  inc     r9
0x140023708  inc     edi
0x14002370a  cmp     r9, rsi
0x14002370d  jb      loc_1400235E7
0x140023713  xor     eax, eax
0x140023715  mov     [r12+rbx-2], ax
0x14002371b  cmp     r9, rsi
0x14002371e  jnz     loc_14002381C
0x140023724  lea     eax, [r14+1]
0x140023728  cmp     edi, eax
0x14002372a  jnz     loc_14002381C
0x140023730  mov     rdx, rbx
0x140023733  mov     rcx, r15
0x140023736  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002373b  nop
0x14002373c  test    rbx, rbx
0x14002373f  jz      short loc_14002374E
0x140023741  mov     edx, 2
0x140023746  mov     rcx, rbx; Block
0x140023749  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002374e  mov     rax, r15
0x140023751  add     rsp, 48h
0x140023755  pop     r15
0x140023757  pop     r14
0x140023759  pop     r13
0x14002375b  pop     r12
0x14002375d  pop     rdi
0x14002375e  pop     rsi
0x14002375f  pop     rbx
0x140023760  pop     rbp
0x140023761  retn
0x140023762  mov     edx, 0CAA60002h; int
0x140023767  lea     rcx, [rbp+pExceptionObject]; this
0x14002376b  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x140023770  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140023777  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14002377b  call    _CxxThrowException_0
0x140023781  mov     edx, 0CAA60003h; int
0x140023786  lea     rcx, [rbp+pExceptionObject]; this
0x14002378a  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x14002378f  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140023796  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14002379a  call    _CxxThrowException_0
0x1400237a0  mov     edx, 0CAA60007h; int
0x1400237a5  lea     rcx, [rbp+pExceptionObject]; this
0x1400237a9  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x1400237ae  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x1400237b5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400237b9  call    _CxxThrowException_0
0x1400237bf  mov     edx, 0CAA60007h; int
0x1400237c4  lea     rcx, [rbp+pExceptionObject]; this
0x1400237c8  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x1400237cd  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x1400237d4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400237d8  call    _CxxThrowException_0
0x1400237de  mov     edx, 0CAA60007h; int
0x1400237e3  lea     rcx, [rbp+pExceptionObject]; this
0x1400237e7  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x1400237ec  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x1400237f3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400237f7  call    _CxxThrowException_0
0x1400237fd  mov     edx, 0CAA60007h; int
0x140023802  lea     rcx, [rbp+pExceptionObject]; this
0x140023806  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x14002380b  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140023812  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140023816  call    _CxxThrowException_0
0x14002381c  mov     edx, 0CAA60007h; int
0x140023821  lea     rcx, [rbp+pExceptionObject]; this
0x140023825  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x14002382a  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140023831  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140023835  call    _CxxThrowException_0
```
