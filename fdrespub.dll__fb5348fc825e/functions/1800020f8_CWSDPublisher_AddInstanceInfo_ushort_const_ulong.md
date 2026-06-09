# CWSDPublisher::AddInstanceInfo(ushort const *,ulong)

- ea: `0x1800020f8`
- end: `0x18000228f`
- name: `?AddInstanceInfo@CWSDPublisher@@IEAAJPEBGK@Z`
- size: `407`
- prototype: `__int64 __fastcall(CWSDPublisher *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180003ae8`

## callees

- `0x180001008`
- `0x180001014`
- `0x18000102c`
- `0x180001f24`
- `0x180001f70`
- `0x1800020f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002234`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002234`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000214f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000214f`

## pseudocode

```c
__int64 __fastcall CWSDPublisher::AddInstanceInfo(CWSDPublisher *this, const unsigned __int16 *a2, int a3)
{
  _QWORD *v6; // rdi
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // r14
  _WORD *v11; // rax
  _WORD *v12; // rdx
  __int64 v13; // rax
  _WORD *v14; // rcx
  _QWORD *v15; // rax
  int v16; // eax
  bool v17; // cf

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v6 = operator new(0x20u);
  if ( v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v9 = (unsigned int)(v8 + 1);
    v10 = (unsigned int)v9;
    v11 = operator new[](saturated_mul(2 * v9, 2u));
    v6[2] = v11;
    v12 = v11;
    if ( v11 )
    {
      v7 = 0;
      if ( v10 )
      {
        if ( v10 <= 0x7FFFFFFF )
        {
          v13 = 2147483646;
          do
          {
            if ( !v13 )
              break;
            if ( !*a2 )
              break;
            *v12++ = *a2++;
            --v13;
            --v10;
          }
          while ( v10 );
          v14 = v12 - 1;
          if ( v10 )
            v14 = v12;
          *v14 = 0;
        }
        else
        {
          *v11 = 0;
        }
      }
      *((_DWORD *)v6 + 6) = a3;
      v15 = (_QWORD *)*((_QWORD *)this + 23);
      *v6 = (char *)this + 176;
      v6[1] = v15;
      *v15 = v6;
      ++*((_DWORD *)this + 21);
      *((_QWORD *)this + 23) = v6;
    }
    else
    {
      operator delete(v6);
      v7 = -2147024882;
    }
  }
  else
  {
    v7 = -2147024882;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v16 = 0;
  if ( v7 )
    v17 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v17 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v16) = !v17;
    if ( v16 )
      WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  }
  return v7;
}

```

## disassembly

```asm
0x1800020f8  push    rbx
0x1800020fa  push    rbp
0x1800020fb  push    rsi
0x1800020fc  push    rdi
0x1800020fd  push    r12
0x1800020ff  push    r13
0x180002101  push    r14
0x180002103  push    r15
0x180002105  sub     rsp, 38h
0x180002109  mov     r12d, r8d
0x18000210c  mov     r15, rdx
0x18000210f  mov     rsi, rcx
0x180002112  mov     rcx, cs:WPP_GLOBAL_Control
0x180002119  lea     r14, WPP_GLOBAL_Control
0x180002120  cmp     rcx, r14
0x180002123  jz      short loc_180002145
0x180002125  cmp     byte ptr [rcx+19h], 4
0x180002129  jb      short loc_180002145
0x18000212b  mov     rcx, [rcx+10h]
0x18000212f  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x180002136  mov     edx, 23h ; '#'
0x18000213b  mov     [rsp+78h+var_58], rsi
0x180002140  call    WPP_SF_sq
0x180002145  lea     rbp, [rsi+88h]
0x18000214c  mov     rcx, rbp; lpCriticalSection
0x18000214f  call    cs:__imp_EnterCriticalSection
0x180002155  mov     ecx, 20h ; ' '; Size
0x18000215a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000215f  xor     r13d, r13d
0x180002162  mov     rdi, rax
0x180002165  test    rax, rax
0x180002168  jnz     short loc_180002174
0x18000216a  mov     ebx, 8007000Eh
0x18000216f  jmp     loc_180002231
0x180002174  or      r8, 0FFFFFFFFFFFFFFFFh
0x180002178  mov     rax, r8
0x18000217b  inc     rax
0x18000217e  cmp     [r15+rax*2], r13w
0x180002183  jnz     short loc_18000217B
0x180002185  inc     eax
0x180002187  mov     r14d, eax
0x18000218a  lea     rcx, [rax+rax]
0x18000218e  mov     eax, 2
0x180002193  mul     rcx
0x180002196  cmovb   rax, r8
0x18000219a  mov     rcx, rax; unsigned __int64
0x18000219d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800021a2  mov     [rdi+10h], rax
0x1800021a6  mov     rdx, rax
0x1800021a9  test    rax, rax
0x1800021ac  jnz     short loc_1800021BD
0x1800021ae  mov     rcx, rdi; Block
0x1800021b1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800021b6  mov     ebx, 8007000Eh
0x1800021bb  jmp     short loc_18000222A
0x1800021bd  mov     ebx, r13d
0x1800021c0  test    r14, r14
0x1800021c3  jz      short loc_18000220A
0x1800021c5  cmp     r14, 7FFFFFFFh
0x1800021cc  jbe     short loc_1800021D4
0x1800021ce  mov     [rax], r13w
0x1800021d2  jmp     short loc_18000220A
0x1800021d4  mov     eax, 7FFFFFFEh
0x1800021d9  test    rax, rax
0x1800021dc  jz      short loc_1800021FB
0x1800021de  movzx   ecx, word ptr [r15]
0x1800021e2  test    cx, cx
0x1800021e5  jz      short loc_1800021FB
0x1800021e7  mov     [rdx], cx
0x1800021ea  add     r15, 2
0x1800021ee  add     rdx, 2
0x1800021f2  dec     rax
0x1800021f5  sub     r14, 1
0x1800021f9  jnz     short loc_1800021D9
0x1800021fb  test    r14, r14
0x1800021fe  lea     rcx, [rdx-2]
0x180002202  cmovnz  rcx, rdx
0x180002206  mov     [rcx], r13w
0x18000220a  mov     [rdi+18h], r12d
0x18000220e  lea     rdx, [rsi+0B0h]
0x180002215  mov     rax, [rdx+8]
0x180002219  mov     [rdi], rdx
0x18000221c  mov     [rdi+8], rax
0x180002220  mov     [rax], rdi
0x180002223  inc     dword ptr [rsi+54h]
0x180002226  mov     [rdx+8], rdi
0x18000222a  lea     r14, WPP_GLOBAL_Control
0x180002231  mov     rcx, rbp; lpCriticalSection
0x180002234  call    cs:__imp_LeaveCriticalSection
0x18000223a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002241  mov     eax, r13d
0x180002244  test    ebx, ebx
0x180002246  jnz     short loc_18000224E
0x180002248  cmp     byte ptr [rcx+19h], 4
0x18000224c  jmp     short loc_180002252
0x18000224e  cmp     byte ptr [rcx+19h], 2
0x180002252  setnb   al
0x180002255  cmp     rcx, r14
0x180002258  jz      short loc_18000227C
0x18000225a  test    eax, eax
0x18000225c  jz      short loc_18000227C
0x18000225e  mov     rcx, [rcx+10h]
0x180002262  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x180002269  mov     edx, 24h ; '$'
0x18000226e  mov     [rsp+78h+var_50], ebx
0x180002272  mov     [rsp+78h+var_58], rsi
0x180002277  call    WPP_SF_sqd
0x18000227c  mov     eax, ebx
0x18000227e  add     rsp, 38h
0x180002282  pop     r15
0x180002284  pop     r14
0x180002286  pop     r13
0x180002288  pop     r12
0x18000228a  pop     rdi
0x18000228b  pop     rsi
0x18000228c  pop     rbp
0x18000228d  pop     rbx
0x18000228e  retn
```
