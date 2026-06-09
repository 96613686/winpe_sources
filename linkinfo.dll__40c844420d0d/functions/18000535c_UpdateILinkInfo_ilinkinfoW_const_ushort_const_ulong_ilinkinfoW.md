# UpdateILinkInfo(_ilinkinfoW const *,ushort const *,ulong *,_ilinkinfoW * *)

- ea: `0x18000535c`
- end: `0x1800053e5`
- name: `?UpdateILinkInfo@@YAHPEBU_ilinkinfoW@@PEBGPEAKPEAPEAU1@@Z`
- size: `137`
- prototype: `int(const struct _ilinkinfoW *, const unsigned __int16 *, unsigned int *, struct _ilinkinfoW **)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001670`

## callees

- `0x180001f10`
- `0x1800043e4`
- `0x180004eb0`
- `0x18000535c`

## pseudocode

```c
__int64 __fastcall UpdateILinkInfo(
        const struct _ilinkinfoW *a1,
        const unsigned __int16 *a2,
        unsigned int *a3,
        struct _ilinkinfoW **a4)
{
  unsigned int ILinkInfo; // ebp
  struct _ilinkinfoW *v8; // rbx
  BOOL v9; // ecx

  *a3 = 0;
  ILinkInfo = CreateILinkInfo(a2, a4);
  if ( ILinkInfo )
  {
    if ( (v8 = *a4, (*((_BYTE *)v8 + 8) & 1) != 0)
      && ((*((_BYTE *)a1 + 8) & 1) == 0 ? (v9 = 1) : (v9 = CompareILinkInfoLocalData((__int64)a1, (__int64)v8) != 0), v9)
      || (*((_BYTE *)v8 + 8) & 2) != 0
      && ((*((_BYTE *)a1 + 8) & 2) == 0
       || (unsigned int)CompareCNRLinks(
                          (__int64)a1 + *((unsigned int *)a1 + 5),
                          (__int64)v8 + *((unsigned int *)v8 + 5))) )
    {
      *a3 |= 1u;
    }
  }
  return ILinkInfo;
}

```

## disassembly

```asm
0x18000535c  push    rbx
0x18000535e  push    rbp
0x18000535f  push    rsi
0x180005360  push    rdi
0x180005361  sub     rsp, 28h
0x180005365  mov     rax, rdx
0x180005368  mov     dword ptr [r8], 0
0x18000536f  mov     rdi, rcx
0x180005372  mov     rdx, r9; struct _ilinkinfoW **
0x180005375  mov     rcx, rax; unsigned __int16 *
0x180005378  mov     rbx, r9
0x18000537b  mov     rsi, r8
0x18000537e  call    ?CreateILinkInfo@@YAHPEBGPEAPEAU_ilinkinfoW@@@Z; CreateILinkInfo(ushort const *,_ilinkinfoW * *)
0x180005383  mov     ebp, eax
0x180005385  test    eax, eax
0x180005387  jz      short loc_1800053D9
0x180005389  mov     rbx, [rbx]
0x18000538c  test    byte ptr [rbx+8], 1
0x180005390  jz      short loc_1800053B5
0x180005392  test    byte ptr [rdi+8], 1
0x180005396  jz      short loc_1800053AC
0x180005398  mov     rdx, rbx
0x18000539b  mov     rcx, rdi
0x18000539e  call    ?CompareILinkInfoLocalData@@YA?AW4_comparisonresult@@PEBU_ilinkinfoW@@0@Z; CompareILinkInfoLocalData(_ilinkinfoW const *,_ilinkinfoW const *)
0x1800053a3  xor     ecx, ecx
0x1800053a5  test    eax, eax
0x1800053a7  setnz   cl
0x1800053aa  jmp     short loc_1800053B1
0x1800053ac  mov     ecx, 1
0x1800053b1  test    ecx, ecx
0x1800053b3  jnz     short loc_1800053D6
0x1800053b5  test    byte ptr [rbx+8], 2
0x1800053b9  jz      short loc_1800053D9
0x1800053bb  test    byte ptr [rdi+8], 2
0x1800053bf  jz      short loc_1800053D6
0x1800053c1  mov     edx, [rbx+14h]
0x1800053c4  mov     ecx, [rdi+14h]
0x1800053c7  add     rdx, rbx
0x1800053ca  add     rcx, rdi
0x1800053cd  call    ?CompareCNRLinks@@YA?AW4_comparisonresult@@PEBU_cnrlink@@0@Z; CompareCNRLinks(_cnrlink const *,_cnrlink const *)
0x1800053d2  test    eax, eax
0x1800053d4  jz      short loc_1800053D9
0x1800053d6  or      dword ptr [rsi], 1
0x1800053d9  mov     eax, ebp
0x1800053db  add     rsp, 28h
0x1800053df  pop     rdi
0x1800053e0  pop     rsi
0x1800053e1  pop     rbp
0x1800053e2  pop     rbx
0x1800053e3  retn
```
