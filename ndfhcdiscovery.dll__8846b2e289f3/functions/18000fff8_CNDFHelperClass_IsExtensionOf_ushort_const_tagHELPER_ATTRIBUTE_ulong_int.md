# CNDFHelperClass::IsExtensionOf(ushort const *,tagHELPER_ATTRIBUTE *,ulong,int *)

- ea: `0x18000fff8`
- end: `0x180010201`
- name: `?IsExtensionOf@CNDFHelperClass@@QEAAJPEBGPEAUtagHELPER_ATTRIBUTE@@KPEAH@Z`
- size: `521`
- prototype: `__int64 __usercall@<rax>(CNDFHelperClass *__hidden this@<rcx>, LPCWSTR lpString1@<rdx>, struct tagHELPER_ATTRIBUTE *@<r8>, unsigned int@<r9d>, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007260`

## callees

- `0x18000ebf8`
- `0x18000f970`
- `0x18000fff8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180010042`
- `KERNEL32!EnterCriticalSection` at `0x180010074`
- `KERNEL32!EnterCriticalSection` at `0x180010042`
- `KERNEL32!EnterCriticalSection` at `0x180010074`
- `KERNEL32!LeaveCriticalSection` at `0x180010065`
- `KERNEL32!LeaveCriticalSection` at `0x18001009a`
- `KERNEL32!LeaveCriticalSection` at `0x1800100b0`
- `KERNEL32!LeaveCriticalSection` at `0x180010065`
- `KERNEL32!LeaveCriticalSection` at `0x18001009a`
- `KERNEL32!LeaveCriticalSection` at `0x1800100b0`
- `KERNEL32!lstrcmpW` at `0x1800100cc`
- `KERNEL32!lstrcmpW` at `0x18001011d`
- `KERNEL32!lstrcmpW` at `0x1800101a4`
- `KERNEL32!lstrcmpW` at `0x1800100cc`
- `KERNEL32!lstrcmpW` at `0x18001011d`
- `KERNEL32!lstrcmpW` at `0x1800101a4`

## pseudocode

```c
__int64 __fastcall CNDFHelperClass::IsExtensionOf(
        struct _RTL_CRITICAL_SECTION *this,
        LPCWSTR lpString1,
        struct tagHELPER_ATTRIBUTE *a3,
        unsigned int a4,
        int *a5)
{
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  LSTATUS v10; // edi
  int matched; // eax
  const WCHAR *OwningThread; // rdx
  __int64 v14; // r15
  _QWORD *v15; // rbx
  int v16; // edi
  const WCHAR *v17; // rcx
  ATTRIBUTE_TYPE type; // eax
  unsigned __int64 DWord; // r9
  __int64 v20; // r10
  unsigned __int64 v21; // r8
  int v22; // edx
  const WCHAR *v23; // rcx

  if ( !lpString1 || !a3 || !a5 )
    return 2147942487LL;
  v9 = this + 8;
  EnterCriticalSection(this + 8);
  if ( !HIDWORD(this[2].OwningThread) )
  {
    v10 = CNDFHelperClass::InitializeBaseData((CNDFHelperClass *)this);
    if ( v10 < 0 )
      goto LABEL_9;
  }
  LeaveCriticalSection(v9);
  EnterCriticalSection(v9);
  if ( !this[7].LockCount )
  {
    matched = CNDFHelperClass::InitializeMatchAttributes((CNDFHelperClass *)this);
    if ( matched < 0 )
    {
      v10 = matched;
LABEL_9:
      LeaveCriticalSection(v9);
      return (unsigned int)v10;
    }
  }
  LeaveCriticalSection(v9);
  OwningThread = (const WCHAR *)this[1].OwningThread;
  if ( OwningThread )
  {
    if ( !lstrcmpW(lpString1, OwningThread) )
    {
      v14 = 0;
      if ( a4 )
      {
        while ( 2 )
        {
          v15 = this[7].OwningThread;
          v16 = 0;
          while ( 1 )
          {
            if ( v15 == this[7].LockSemaphore )
              goto LABEL_35;
            v17 = v15[3] < 8u ? (const WCHAR *)v15 : (const WCHAR *)*v15;
            if ( !lstrcmpW(v17, a3[v14].pwszName) )
            {
              type = a3[v14].type;
              if ( *((_DWORD *)v15 + 8) == type )
                break;
            }
            v15 += 13;
          }
          if ( type == AT_UINT32 )
          {
            if ( *((_DWORD *)v15 + 24) != a3[v14].Boolean )
              goto LABEL_35;
          }
          else
          {
            if ( type == AT_STRING )
            {
              v23 = (const WCHAR *)(v15 + 8);
              if ( v15[11] >= 8u )
                v23 = *(const WCHAR **)v23;
              LOBYTE(v16) = lstrcmpW(v23, a3[v14].PWStr) == 0;
            }
            else
            {
              if ( type != AT_OCTET_STRING )
                goto LABEL_35;
              DWord = a3[v14].DWord;
              v20 = v15[5];
              LOBYTE(v16) = DWord == v15[6] - v20;
              if ( a3[v14].Boolean )
              {
                v21 = 0;
                while ( v16 )
                {
                  v22 = 0;
                  if ( a3[v14].OctetString.lpValue[v21] == *(_BYTE *)(v20 + v21) )
                    v22 = v16;
                  ++v21;
                  v16 = v22;
                  if ( v21 >= DWord )
                    goto LABEL_34;
                }
LABEL_35:
                *a5 = 0;
                if ( !v16 )
                  return 0;
                break;
              }
            }
LABEL_34:
            if ( !v16 )
              goto LABEL_35;
          }
          v14 = (unsigned int)(v14 + 1);
          if ( (unsigned int)v14 < a4 )
            continue;
          break;
        }
        *a5 = 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000fff8  push    rbx
0x18000fffa  push    rbp
0x18000fffb  push    rsi
0x18000fffc  push    rdi
0x18000fffd  push    r12
0x18000ffff  push    r13
0x180010001  push    r14
0x180010003  push    r15
0x180010005  sub     rsp, 28h
0x180010009  mov     r13d, r9d
0x18001000c  mov     rbp, r8
0x18001000f  mov     r14, rdx
0x180010012  mov     rsi, rcx
0x180010015  test    rdx, rdx
0x180010018  jz      loc_1800101EA
0x18001001e  test    r8, r8
0x180010021  jz      loc_1800101EA
0x180010027  mov     r12, [rsp+68h+arg_20]
0x18001002f  test    r12, r12
0x180010032  jz      loc_1800101EA
0x180010038  lea     rbx, [rcx+140h]
0x18001003f  mov     rcx, rbx; lpCriticalSection
0x180010042  call    cs:__imp_EnterCriticalSection
0x180010049  nop     dword ptr [rax+rax+00h]
0x18001004e  cmp     dword ptr [rsi+64h], 0
0x180010052  jnz     short loc_180010062
0x180010054  mov     rcx, rsi; this
0x180010057  call    ?InitializeBaseData@CNDFHelperClass@@AEAAJXZ; CNDFHelperClass::InitializeBaseData(void)
0x18001005c  mov     edi, eax
0x18001005e  test    eax, eax
0x180010060  js      short loc_180010097
0x180010062  mov     rcx, rbx; lpCriticalSection
0x180010065  call    cs:__imp_LeaveCriticalSection
0x18001006c  nop     dword ptr [rax+rax+00h]
0x180010071  mov     rcx, rbx; lpCriticalSection
0x180010074  call    cs:__imp_EnterCriticalSection
0x18001007b  nop     dword ptr [rax+rax+00h]
0x180010080  cmp     dword ptr [rsi+120h], 0
0x180010087  jnz     short loc_1800100AD
0x180010089  mov     rcx, rsi; this
0x18001008c  call    ?InitializeMatchAttributes@CNDFHelperClass@@AEAAJXZ; CNDFHelperClass::InitializeMatchAttributes(void)
0x180010091  test    eax, eax
0x180010093  jns     short loc_1800100AD
0x180010095  mov     edi, eax
0x180010097  mov     rcx, rbx; lpCriticalSection
0x18001009a  call    cs:__imp_LeaveCriticalSection
0x1800100a1  nop     dword ptr [rax+rax+00h]
0x1800100a6  mov     eax, edi
0x1800100a8  jmp     loc_1800101EF
0x1800100ad  mov     rcx, rbx; lpCriticalSection
0x1800100b0  call    cs:__imp_LeaveCriticalSection
0x1800100b7  nop     dword ptr [rax+rax+00h]
0x1800100bc  mov     rdx, [rsi+38h]; lpString2
0x1800100c0  test    rdx, rdx
0x1800100c3  jz      loc_1800101CE
0x1800100c9  mov     rcx, r14; lpString1
0x1800100cc  call    cs:__imp_lstrcmpW
0x1800100d3  nop     dword ptr [rax+rax+00h]
0x1800100d8  test    eax, eax
0x1800100da  jnz     loc_1800101CE
0x1800100e0  xor     r15d, r15d
0x1800100e3  test    r13d, r13d
0x1800100e6  jz      loc_1800101CE
0x1800100ec  mov     rbx, [rsi+128h]
0x1800100f3  xor     edi, edi
0x1800100f5  cmp     rbx, [rsi+130h]
0x1800100fc  jz      loc_1800101BA
0x180010102  lea     r14, [r15+r15*8]
0x180010106  add     r14, r14
0x180010109  cmp     qword ptr [rbx+18h], 8
0x18001010e  jb      short loc_180010115
0x180010110  mov     rcx, [rbx]
0x180010113  jmp     short loc_180010118
0x180010115  mov     rcx, rbx; lpString1
0x180010118  mov     rdx, [rbp+r14*8+0]; lpString2
0x18001011d  call    cs:__imp_lstrcmpW
0x180010124  nop     dword ptr [rax+rax+00h]
0x180010129  test    eax, eax
0x18001012b  jnz     short loc_180010137
0x18001012d  mov     eax, [rbp+r14*8+8]
0x180010132  cmp     [rbx+20h], eax
0x180010135  jz      short loc_18001013D
0x180010137  add     rbx, 68h ; 'h'
0x18001013b  jmp     short loc_1800100F5
0x18001013d  cmp     eax, 7
0x180010140  jz      loc_1800101D2
0x180010146  cmp     eax, 0Ah
0x180010149  jz      short loc_180010191
0x18001014b  cmp     eax, 0Eh
0x18001014e  jnz     short loc_1800101BA
0x180010150  mov     r9d, [rbp+r14*8+10h]
0x180010155  mov     r10, [rbx+28h]
0x180010159  mov     rax, [rbx+30h]
0x18001015d  sub     rax, r10
0x180010160  cmp     r9, rax
0x180010163  setz    dil
0x180010167  test    r9, r9
0x18001016a  jz      short loc_1800101B6
0x18001016c  xor     r8d, r8d
0x18001016f  test    edi, edi
0x180010171  jz      short loc_1800101BA
0x180010173  mov     al, [r10+r8]
0x180010177  xor     edx, edx
0x180010179  mov     rcx, [rbp+r14*8+18h]
0x18001017e  cmp     [r8+rcx], al
0x180010182  cmovz   edx, edi
0x180010185  inc     r8
0x180010188  mov     edi, edx
0x18001018a  cmp     r8, r9
0x18001018d  jb      short loc_18001016F
0x18001018f  jmp     short loc_1800101B6
0x180010191  cmp     qword ptr [rbx+58h], 8
0x180010196  lea     rcx, [rbx+40h]
0x18001019a  jb      short loc_18001019F
0x18001019c  mov     rcx, [rcx]; lpString1
0x18001019f  mov     rdx, [rbp+r14*8+10h]; lpString2
0x1800101a4  call    cs:__imp_lstrcmpW
0x1800101ab  nop     dword ptr [rax+rax+00h]
0x1800101b0  test    eax, eax
0x1800101b2  setz    dil
0x1800101b6  test    edi, edi
0x1800101b8  jnz     short loc_1800101DC
0x1800101ba  mov     dword ptr [r12], 0
0x1800101c2  test    edi, edi
0x1800101c4  jz      short loc_1800101CE
0x1800101c6  mov     dword ptr [r12], 1
0x1800101ce  xor     eax, eax
0x1800101d0  jmp     short loc_1800101EF
0x1800101d2  mov     eax, [rbp+r14*8+10h]
0x1800101d7  cmp     [rbx+60h], eax
0x1800101da  jnz     short loc_1800101BA
0x1800101dc  inc     r15d
0x1800101df  cmp     r15d, r13d
0x1800101e2  jb      loc_1800100EC
0x1800101e8  jmp     short loc_1800101C6
0x1800101ea  mov     eax, 80070057h
0x1800101ef  add     rsp, 28h
0x1800101f3  pop     r15
0x1800101f5  pop     r14
0x1800101f7  pop     r13
0x1800101f9  pop     r12
0x1800101fb  pop     rdi
0x1800101fc  pop     rsi
0x1800101fd  pop     rbp
0x1800101fe  pop     rbx
0x1800101ff  retn
```
