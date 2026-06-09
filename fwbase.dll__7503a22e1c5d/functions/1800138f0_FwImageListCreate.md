# FwImageListCreate

- ea: `0x1800138f0`
- end: `0x1800139f7`
- name: `FwImageListCreate`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800138b0`

## callees

- `0x180002b30`
- `0x180004750`
- `0x1800047e0`
- `0x180004870`
- `0x180006ac0`
- `0x18000c060`
- `0x1800138f0`

## string_xrefs

- `0x180013960`: `FwImageListCreate`
- `0x1800139b3`: `FwImageListCreate`
- `0x1800139d6`: `FwImageListCreate`

## pseudocode

```c
__int64 __fastcall FwImageListCreate(__int64 a1, __int64 a2, _OWORD *a3)
{
  int v3; // esi
  int ExpandedCanonicalLongPathName; // eax
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int128 v10; // [rsp+20h] [rbp-10h] BYREF
  int v11; // [rsp+60h] [rbp+30h] BYREF
  __int64 v12; // [rsp+68h] [rbp+38h] BYREF

  v3 = 0;
  v12 = 0;
  v10 = 0u;
  *a3 = 0;
  v11 = 0;
  ExpandedCanonicalLongPathName = FwSizeTMultiply(1, 8, &v12);
  v7 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName < 0 )
  {
LABEL_11:
    FwReportReturnError("FwImageListCreate", (unsigned int)ExpandedCanonicalLongPathName);
LABEL_12:
    FwArrayDestroy(8, FwImageListEntryDestroy, &v10);
    return (unsigned int)FwReportReturnError("FwImageListCreate", v7);
  }
  *((_QWORD *)&v10 + 1) = FwAlloc(v12, v6);
  if ( *((_QWORD *)&v10 + 1) )
  {
    v8 = 0;
    while ( 1 )
    {
      ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(
                                        (&off_180031240)[v8],
                                        (_QWORD *)(*((_QWORD *)&v10 + 1) + 8 * v8),
                                        &v11);
      v7 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName < 0 )
        break;
      if ( v11 )
        LODWORD(v10) = ++v3;
      v8 = (unsigned int)(v8 + 1);
      if ( (_DWORD)v8 )
      {
        *a3 = v10;
        return v7;
      }
    }
    goto LABEL_11;
  }
  v7 = FwReportErrorAsWinError("FwImageListCreate", "FwAlloc", 8);
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_12;
  return v7;
}

```

## disassembly

```asm
0x1800138f0  mov     [rsp-28h+arg_10], rbx
0x1800138f5  mov     [rsp-28h+arg_8], rdx
0x1800138fa  mov     [rsp-28h+arg_0], ecx
0x1800138fe  push    rbp
0x1800138ff  push    rsi
0x180013900  push    rdi
0x180013901  push    r14
0x180013903  push    r15
0x180013905  mov     rbp, rsp
0x180013908  sub     rsp, 30h
0x18001390c  xor     esi, esi
0x18001390e  mov     [rbp+arg_8], 0
0x180013916  xorps   xmm0, xmm0
0x180013919  mov     qword ptr [rbp+var_10], rsi
0x18001391d  mov     r15, r8
0x180013920  mov     qword ptr [rbp+var_10+8], rsi
0x180013924  movups  xmmword ptr [r8], xmm0
0x180013928  lea     edx, [rsi+8]
0x18001392b  mov     [rbp+arg_0], esi
0x18001392e  lea     ecx, [rsi+1]
0x180013931  lea     r8, [rbp+arg_8]
0x180013935  call    FwSizeTMultiply
0x18001393a  mov     ebx, eax
0x18001393c  test    eax, eax
0x18001393e  js      short loc_1800139B1
0x180013940  mov     rcx, [rbp+arg_8]
0x180013944  call    FwAlloc
0x180013949  mov     qword ptr [rbp+var_10+8], rax
0x18001394d  mov     r14, rax
0x180013950  test    rax, rax
0x180013953  jnz     short loc_180013974
0x180013955  lea     r8d, [rsi+8]
0x180013959  lea     rdx, aFwalloc_0; "FwAlloc"
0x180013960  lea     rcx, aFwimagelistcre; "FwImageListCreate"
0x180013967  call    FwReportErrorAsWinError
0x18001396c  mov     ebx, eax
0x18001396e  test    eax, eax
0x180013970  jns     short loc_1800139E4
0x180013972  jmp     short loc_1800139BF
0x180013974  xor     edi, edi
0x180013976  lea     rax, off_180031240; "%SystemRoot%\\System32\\svchost.exe"
0x18001397d  mov     rcx, [rax+rdi*8]
0x180013981  lea     rdx, [r14+rdi*8]
0x180013985  lea     r8, [rbp+arg_0]
0x180013989  call    FwGetExpandedCanonicalLongPathName
0x18001398e  mov     ebx, eax
0x180013990  test    eax, eax
0x180013992  js      short loc_1800139B1
0x180013994  cmp     [rbp+arg_0], 0
0x180013998  jz      short loc_18001399F
0x18001399a  inc     esi
0x18001399c  mov     dword ptr [rbp+var_10], esi
0x18001399f  inc     edi
0x1800139a1  cmp     edi, 1
0x1800139a4  jb      short loc_180013976
0x1800139a6  movups  xmm0, [rbp+var_10]
0x1800139aa  movdqu  xmmword ptr [r15], xmm0
0x1800139af  jmp     short loc_1800139E4
0x1800139b1  mov     edx, eax
0x1800139b3  lea     rcx, aFwimagelistcre; "FwImageListCreate"
0x1800139ba  call    FwReportReturnError
0x1800139bf  lea     r8, [rbp+var_10]
0x1800139c3  mov     ecx, 8
0x1800139c8  lea     rdx, ?FwImageListEntryDestroy@@YAXPEAPEAG@Z; FwImageListEntryDestroy(ushort * *)
0x1800139cf  call    FwArrayDestroy
0x1800139d4  mov     edx, ebx
0x1800139d6  lea     rcx, aFwimagelistcre; "FwImageListCreate"
0x1800139dd  call    FwReportReturnError
0x1800139e2  mov     ebx, eax
0x1800139e4  mov     eax, ebx
0x1800139e6  mov     rbx, [rsp+30h+arg_10]
0x1800139eb  add     rsp, 30h
0x1800139ef  pop     r15
0x1800139f1  pop     r14
0x1800139f3  pop     rdi
0x1800139f4  pop     rsi
0x1800139f5  pop     rbp
0x1800139f6  retn
```
