# CADMCOMW::CheckNotificationScope(ushort const *,ulong,ushort const *,ulong,ulong)

- ea: `0x180003048`
- end: `0x18000315a`
- name: `?CheckNotificationScope@CADMCOMW@@AEAAJPEBGK0KK@Z`
- size: `274`
- prototype: `int(CADMCOMW *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003590`

## callees

- `0x180003048`
- `0x18000fb2a`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x1800030b4`
- `IisRTL!PuDbgPrint` at `0x1800030b4`

## string_xrefs

- `0x1800030a8`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x1800030a1`: `Checking the path %S with length %d against the scope [%S] with length %d and flags 0x%08x.\n`
- `0x18000308c`: `CADMCOMW::CheckNotificationScope`

## pseudocode

```c
__int64 __fastcall CADMCOMW::CheckNotificationScope(
        CADMCOMW *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        char *a4,
        unsigned int a5,
        unsigned int a6)
{
  unsigned int v6; // ebx
  const wchar_t *v9; // rdi
  char *v10; // rbp
  int v11; // ecx
  int v12; // eax

  v6 = 0;
  v9 = a2;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
      8337,
      "CADMCOMW::CheckNotificationScope",
      "Checking the path %S with length %d against the scope [%S] with length %d and flags 0x%08x.\n",
      a2,
      a3,
      (const wchar_t *)a4,
      a5,
      a6);
  if ( a5 != 1 )
  {
    if ( v9 && a4 && a3 && a5 && (a6 & 0xFFFFFFFC) == 0 )
    {
      if ( ((a6 & 2) == 0 || a3 < a5 || wcsncmp_0((const wchar_t *)a4, v9, a5 - 1))
        && ((a6 & 1) == 0 || a3 > a5 || wcsncmp_0(v9, (const wchar_t *)a4, a3 - 1)) )
      {
        if ( a6 || a3 != a5 )
          return 1;
        v10 = (char *)(a4 - (char *)v9);
        do
        {
          v11 = *(unsigned __int16 *)&v10[(_QWORD)v9];
          v12 = *v9 - v11;
          if ( v12 )
            break;
          ++v9;
        }
        while ( v11 );
        if ( v12 )
          return 1;
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180003048  mov     rax, rsp
0x18000304b  push    rbx
0x18000304c  push    rbp
0x18000304d  push    rsi
0x18000304e  push    rdi
0x18000304f  push    r14
0x180003051  push    r15
0x180003053  sub     rsp, 58h
0x180003057  mov     r15d, [rsp+88h+arg_28]
0x18000305f  xor     ebx, ebx
0x180003061  test    byte ptr cs:g_dwDebugFlags, 3
0x180003068  mov     rbp, r9
0x18000306b  mov     esi, [rsp+88h+arg_20]
0x180003072  mov     r14d, r8d
0x180003075  mov     rdi, rdx
0x180003078  jz      short loc_1800030BA
0x18000307a  mov     rcx, cs:g_pDebug
0x180003081  mov     [rax-40h], r15d
0x180003085  mov     [rax-48h], esi
0x180003088  mov     [rax-50h], r9
0x18000308c  lea     r9, aCadmcomwCheckn; "CADMCOMW::CheckNotificationScope"
0x180003093  mov     [rax-58h], r8d
0x180003097  mov     r8d, 2091h
0x18000309d  mov     [rax-60h], rdx
0x1800030a1  lea     rax, aCheckingThePat; "Checking the path %S with length %d aga"...
0x1800030a8  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x1800030af  mov     [rsp+88h+var_68], rax
0x1800030b4  call    cs:__imp_PuDbgPrint
0x1800030ba  cmp     esi, 1
0x1800030bd  jz      loc_18000314B
0x1800030c3  test    rdi, rdi
0x1800030c6  jz      short loc_180003146
0x1800030c8  test    rbp, rbp
0x1800030cb  jz      short loc_180003146
0x1800030cd  test    r14d, r14d
0x1800030d0  jz      short loc_180003146
0x1800030d2  test    esi, esi
0x1800030d4  jz      short loc_180003146
0x1800030d6  test    r15d, 0FFFFFFFCh
0x1800030dd  jnz     short loc_180003146
0x1800030df  test    r15b, 2
0x1800030e3  jz      short loc_1800030FD
0x1800030e5  cmp     r14d, esi
0x1800030e8  jb      short loc_1800030FD
0x1800030ea  lea     r8d, [rsi-1]; MaxCount
0x1800030ee  mov     rdx, rdi; String2
0x1800030f1  mov     rcx, rbp; String1
0x1800030f4  call    wcsncmp_0
0x1800030f9  test    eax, eax
0x1800030fb  jz      short loc_18000314B
0x1800030fd  test    r15b, 1
0x180003101  jz      short loc_18000311B
0x180003103  cmp     r14d, esi
0x180003106  ja      short loc_18000311B
0x180003108  lea     r8d, [r14-1]; MaxCount
0x18000310c  mov     rdx, rbp; String2
0x18000310f  mov     rcx, rdi; String1
0x180003112  call    wcsncmp_0
0x180003117  test    eax, eax
0x180003119  jz      short loc_18000314B
0x18000311b  test    r15d, r15d
0x18000311e  jnz     short loc_18000313F
0x180003120  cmp     r14d, esi
0x180003123  jnz     short loc_18000313F
0x180003125  sub     rbp, rdi
0x180003128  movzx   eax, word ptr [rdi]
0x18000312b  movzx   ecx, word ptr [rdi+rbp]
0x18000312f  sub     eax, ecx
0x180003131  jnz     short loc_18000313B
0x180003133  add     rdi, 2
0x180003137  test    ecx, ecx
0x180003139  jnz     short loc_180003128
0x18000313b  test    eax, eax
0x18000313d  jz      short loc_18000314B
0x18000313f  mov     ebx, 1
0x180003144  jmp     short loc_18000314B
0x180003146  mov     ebx, 80070057h
0x18000314b  mov     eax, ebx
0x18000314d  add     rsp, 58h
0x180003151  pop     r15
0x180003153  pop     r14
0x180003155  pop     rdi
0x180003156  pop     rsi
0x180003157  pop     rbp
0x180003158  pop     rbx
0x180003159  retn
```
