# CanonicalizeTag(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort * *,ulong *)

- ea: `0x1800110e4`
- end: `0x180011244`
- name: `?CanonicalizeTag@@YAJPEBGK0KW4SyncMLElemType@@PEAPEAGPEAK@Z`
- size: `352`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, int, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000fee0`
- `0x180021ae0`

## callees

- `0x1800029b0`
- `0x1800110e4`
- `0x18001613c`
- `0x180016278`

## import_xrefs

- `DMCmnUtils!InvStrCmpNIW` at `0x18001116a`
- `DMCmnUtils!InvStrCmpNIW` at `0x1800111b2`
- `DMCmnUtils!InvStrCmpNIW` at `0x1800111d9`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001116a`
- `DMCmnUtils!InvStrCmpNIW` at `0x1800111b2`
- `DMCmnUtils!InvStrCmpNIW` at `0x1800111d9`
- `DMCmnUtils!CopyString` at `0x180011214`
- `DMCmnUtils!CopyString` at `0x180011214`

## string_xrefs

- `0x180011160`: `http://schemas.microsoft.com/MobileDevice/DM`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CanonicalizeTag(
        const unsigned __int16 *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        int a5,
        unsigned __int16 **a6,
        unsigned int *a7)
{
  const unsigned __int16 *v7; // r12
  unsigned __int64 v9; // rbp
  unsigned __int64 v11; // rdi
  int v12; // ebx
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rcx
  unsigned int *v15; // r14
  size_t pcchLength[11]; // [rsp+30h] [rbp-58h] BYREF

  v7 = off_18003E470;
  v9 = a4;
  v11 = a2;
  pcchLength[0] = 0;
  if ( !off_18003E470 )
    return (unsigned int)-2147024809;
  v12 = StringLengthWorkerW(off_18003E470, 0x7FFFFFFFu, pcchLength);
  if ( v12 >= 0 )
  {
    *a6 = 0;
    if ( (_DWORD)v9 && *a3 )
    {
      if ( (_DWORD)v9 == 44 && !InvStrCmpNIW(L"http://schemas.microsoft.com/MobileDevice/DM", a3, 0x2Cu) )
      {
        v15 = a7;
        v12 = PrefixProp(v14, v13, a1, v11, a6, a7);
        if ( v12 < 0 )
          return (unsigned int)v12;
        goto LABEL_16;
      }
      if ( pcchLength[0] != v9 || InvStrCmpNIW(v7, a3, v9) )
      {
        if ( !(unsigned int)IsValidNamespace(a3, v9) )
          return (unsigned int)-2102788095;
      }
      else if ( a5 != 23 && InvStrCmpNIW(a1, off_18003E2E8[0], v11) )
      {
        return (unsigned int)-2102788095;
      }
    }
    v15 = a7;
LABEL_16:
    if ( !*a6 )
    {
      v12 = CopyString(a1, v11, a6);
      if ( v12 >= 0 )
        *v15 = v11;
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800110e4  push    rbx
0x1800110e6  push    rbp
0x1800110e7  push    rsi
0x1800110e8  push    rdi
0x1800110e9  push    r12
0x1800110eb  push    r13
0x1800110ed  push    r14
0x1800110ef  push    r15
0x1800110f1  sub     rsp, 48h
0x1800110f5  mov     r12, cs:off_18003E470; "syncml:metinf"
0x1800110fc  mov     r14, r8
0x1800110ff  mov     ebp, r9d
0x180011102  mov     r13, rcx
0x180011105  mov     edi, edx
0x180011107  mov     [rsp+88h+pcchLength], 0
0x180011110  test    r12, r12
0x180011113  jz      loc_18001122B
0x180011119  lea     r8, [rsp+88h+pcchLength]; pcchLength
0x18001111e  mov     edx, 7FFFFFFFh; cchMax
0x180011123  mov     rcx, r12; psz
0x180011126  call    StringLengthWorkerW
0x18001112b  mov     ebx, eax
0x18001112d  test    eax, eax
0x18001112f  js      loc_180011230
0x180011135  mov     rsi, [rsp+88h+arg_28]
0x18001113d  mov     qword ptr [rsi], 0
0x180011144  test    ebp, ebp
0x180011146  jz      loc_1800111FE
0x18001114c  xor     eax, eax
0x18001114e  cmp     ax, [r14]
0x180011152  jz      loc_1800111FE
0x180011158  cmp     ebp, 2Ch ; ','
0x18001115b  jnz     short loc_1800111A2
0x18001115d  mov     r8d, ebp
0x180011160  lea     rcx, ?gc_szMSFTNamespace@@3QBGB; "http://schemas.microsoft.com/MobileDevi"...
0x180011167  mov     rdx, r14
0x18001116a  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x180011171  nop     dword ptr [rax+rax+00h]
0x180011176  test    eax, eax
0x180011178  jnz     short loc_1800111A2
0x18001117a  mov     r14, [rsp+88h+arg_30]
0x180011182  mov     r9d, edi; unsigned int
0x180011185  mov     [rsp+88h+var_60], r14; unsigned int *
0x18001118a  mov     r8, r13; unsigned __int16 *
0x18001118d  mov     [rsp+88h+var_68], rsi; unsigned __int16 **
0x180011192  call    ?PrefixProp@@YAJPEBGK0KPEAPEAGPEAK@Z; PrefixProp(ushort const *,ulong,ushort const *,ulong,ushort * *,ulong *)
0x180011197  mov     ebx, eax
0x180011199  test    eax, eax
0x18001119b  jns     short loc_180011206
0x18001119d  jmp     loc_180011230
0x1800111a2  cmp     [rsp+88h+pcchLength], rbp
0x1800111a7  jnz     short loc_1800111F0
0x1800111a9  mov     r8, rbp
0x1800111ac  mov     rdx, r14
0x1800111af  mov     rcx, r12
0x1800111b2  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x1800111b9  nop     dword ptr [rax+rax+00h]
0x1800111be  test    eax, eax
0x1800111c0  jnz     short loc_1800111F0
0x1800111c2  cmp     [rsp+88h+arg_20], 17h
0x1800111ca  jz      short loc_1800111FE
0x1800111cc  mov     rdx, cs:off_18003E2E8; "Meta"
0x1800111d3  mov     r8, rdi
0x1800111d6  mov     rcx, r13
0x1800111d9  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x1800111e0  nop     dword ptr [rax+rax+00h]
0x1800111e5  test    eax, eax
0x1800111e7  jz      short loc_1800111FE
0x1800111e9  mov     ebx, 82AA0001h
0x1800111ee  jmp     short loc_180011230
0x1800111f0  mov     edx, ebp; unsigned int
0x1800111f2  mov     rcx, r14; unsigned __int16 *
0x1800111f5  call    ?IsValidNamespace@@YAHPEBGK@Z; IsValidNamespace(ushort const *,ulong)
0x1800111fa  test    eax, eax
0x1800111fc  jz      short loc_1800111E9
0x1800111fe  mov     r14, [rsp+88h+arg_30]
0x180011206  cmp     qword ptr [rsi], 0
0x18001120a  jnz     short loc_180011230
0x18001120c  mov     r8, rsi
0x18001120f  mov     edx, edi
0x180011211  mov     rcx, r13
0x180011214  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001121b  nop     dword ptr [rax+rax+00h]
0x180011220  mov     ebx, eax
0x180011222  test    eax, eax
0x180011224  js      short loc_180011230
0x180011226  mov     [r14], edi
0x180011229  jmp     short loc_180011230
0x18001122b  mov     ebx, 80070057h
0x180011230  mov     eax, ebx
0x180011232  add     rsp, 48h
0x180011236  pop     r15
0x180011238  pop     r14
0x18001123a  pop     r13
0x18001123c  pop     r12
0x18001123e  pop     rdi
0x18001123f  pop     rsi
0x180011240  pop     rbp
0x180011241  pop     rbx
0x180011242  retn
```
