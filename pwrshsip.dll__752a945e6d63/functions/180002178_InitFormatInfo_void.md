# InitFormatInfo(void)

- ea: `0x180002178`
- end: `0x180002536`
- name: `?InitFormatInfo@@YAXXZ`
- size: `958`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800019c0`
- `0x180001d90`
- `0x180001fa0`
- `0x180002720`

## callees

- `0x180002178`

## string_xrefs

- `0x180002250`: `ps1xml`
- `0x18000240c`: `cdxml`

## pseudocode

```c
void InitFormatInfo(void)
{
  if ( !dword_180009624 )
  {
    qword_180009870 = 0;
    dword_180009624 = 1;
    dword_180009878 = 33;
    qword_180009840[0] = (__int64)L"ps1";
    dword_18000987C = 29;
    qword_180009848 = (__int64)L"\r\n# SIG # Begin signature block\r\n";
    dword_180009880 = 29;
    qword_180009850 = (__int64)L"# SIG # Begin signature block";
    dword_180009884 = 27;
    qword_180009858 = (__int64)L"# SIG # End signature block\r\n";
    qword_180009888 = 2;
    qword_180009860 = (__int64)L"# SIG # End signature block";
    qword_180009898 = (__int64)L"\r\n<!-- SIG # Begin signature block -->\r\n";
    qword_180009868 = (__int64)L"# ";
    qword_1800098A0 = (__int64)L"<!-- SIG # Begin signature block -->";
    qword_180009890 = (__int64)L"ps1xml";
    qword_1800098A8 = (__int64)L"<!-- SIG # End signature block -->\r\n";
    qword_1800098E0 = (__int64)L"psc1";
    qword_1800098B0 = (__int64)L"<!-- SIG # End signature block -->";
    qword_180009930 = (__int64)L"psd1";
    qword_1800098B8 = (__int64)L"<!-- ";
    qword_180009938 = (__int64)L"\r\n# SIG # Begin signature block\r\n";
    qword_1800098C0 = (__int64)L" -->";
    qword_180009940 = (__int64)L"# SIG # Begin signature block";
    qword_180009948 = (__int64)L"# SIG # End signature block\r\n";
    qword_180009950 = (__int64)L"# SIG # End signature block";
    qword_180009958 = (__int64)L"# ";
    qword_180009980 = (__int64)L"psm1";
    qword_180009988 = (__int64)L"\r\n# SIG # Begin signature block\r\n";
    dword_1800098C8 = 40;
    dword_1800098CC = 36;
    dword_1800098D0 = 36;
    dword_1800098D4 = 34;
    dword_1800098D8 = 5;
    dword_1800098DC = 4;
    qword_1800098E8 = (__int64)L"\r\n<!-- SIG # Begin signature block -->\r\n";
    qword_1800098F0 = (__int64)L"<!-- SIG # Begin signature block -->";
    qword_1800098F8 = (__int64)L"<!-- SIG # End signature block -->\r\n";
    qword_180009900 = (__int64)L"<!-- SIG # End signature block -->";
    qword_180009908 = (__int64)L"<!-- ";
    qword_180009910 = (__int64)L" -->";
    dword_180009918 = 40;
    dword_18000991C = 36;
    dword_180009920 = 36;
    dword_180009924 = 34;
    dword_180009928 = 5;
    dword_18000992C = 4;
    qword_180009960 = 0;
    dword_180009968 = 33;
    dword_18000996C = 29;
    dword_180009970 = 29;
    dword_180009974 = 27;
    qword_180009978 = 2;
    qword_1800099B0 = 0;
    qword_180009990 = (__int64)L"# SIG # Begin signature block";
    qword_180009998 = (__int64)L"# SIG # End signature block\r\n";
    qword_1800099A0 = (__int64)L"# SIG # End signature block";
    qword_1800099A8 = (__int64)L"# ";
    qword_1800099D0 = (__int64)L"cdxml";
    qword_180009A20 = (__int64)L"mof";
    qword_180009A28 = (__int64)L"\r\n/* SIG # Begin signature block */\r\n";
    qword_180009A30 = (__int64)L"/* SIG # Begin signature block */";
    qword_180009A38 = (__int64)L"/* SIG # End signature block */\r\n";
    qword_180009A40 = (__int64)L"/* SIG # End signature block */";
    qword_180009A48 = (__int64)L"/* ";
    qword_180009A50 = (__int64)L" */";
    dword_180009A5C = 33;
    dword_180009A60 = 33;
    dword_180009A68 = 3;
    dword_180009A6C = 3;
    dword_1800099B8 = 33;
    dword_1800099BC = 29;
    dword_1800099C0 = 29;
    dword_1800099C4 = 27;
    qword_1800099C8 = 2;
    qword_1800099D8 = (__int64)L"\r\n<!-- SIG # Begin signature block -->\r\n";
    qword_1800099E0 = (__int64)L"<!-- SIG # Begin signature block -->";
    qword_1800099E8 = (__int64)L"<!-- SIG # End signature block -->\r\n";
    qword_1800099F0 = (__int64)L"<!-- SIG # End signature block -->";
    qword_1800099F8 = (__int64)L"<!-- ";
    qword_180009A00 = (__int64)L" -->";
    dword_180009A08 = 40;
    dword_180009A0C = 36;
    dword_180009A10 = 36;
    dword_180009A14 = 34;
    dword_180009A18 = 5;
    dword_180009A1C = 4;
    dword_180009A58 = 37;
    dword_180009A64 = 31;
  }
}

```

## disassembly

```asm
0x180002178  push    rbx
0x18000217a  push    rbp
0x18000217b  push    rsi
0x18000217c  push    rdi
0x18000217d  push    r13
0x18000217f  push    r14
0x180002181  xor     ecx, ecx
0x180002183  cmp     cs:dword_180009624, ecx
0x180002189  jnz     loc_18000252D
0x18000218f  lea     r13d, [rcx+1Dh]
0x180002193  mov     cs:qword_180009870, rcx
0x18000219a  lea     r10d, [rcx+24h]
0x18000219e  mov     cs:dword_180009624, 1
0x1800021a8  lea     rax, aPs1; "ps1"
0x1800021af  mov     cs:dword_180009878, 21h ; '!'
0x1800021b9  mov     cs:qword_180009840, rax
0x1800021c0  lea     edx, [rcx+5]
0x1800021c3  lea     rax, aSigBeginSignat; "\r\n# SIG # Begin signature block\r\n"
0x1800021ca  mov     cs:dword_18000987C, r13d
0x1800021d1  mov     cs:qword_180009848, rax
0x1800021d8  lea     r9d, [rcx+28h]
0x1800021dc  lea     rax, aSigBeginSignat_0; "# SIG # Begin signature block"
0x1800021e3  mov     cs:dword_180009880, r13d
0x1800021ea  mov     cs:qword_180009850, rax
0x1800021f1  lea     r8d, [rcx+22h]
0x1800021f5  lea     rax, aSigEndSignatur; "# SIG # End signature block\r\n"
0x1800021fc  mov     cs:dword_180009884, 1Bh
0x180002206  mov     cs:qword_180009858, rax
0x18000220d  lea     r14, aSigBeginSignat_1; "\r\n<!-- SIG # Begin signature block --"...
0x180002214  lea     rax, aSigEndSignatur_0; "# SIG # End signature block"
0x18000221b  mov     cs:qword_180009888, 2
0x180002226  mov     cs:qword_180009860, rax
0x18000222d  lea     rbp, aSigBeginSignat_2; "<!-- SIG # Begin signature block -->"
0x180002234  lea     rax, asc_180007834; "# "
0x18000223b  mov     cs:qword_180009898, r14
0x180002242  mov     cs:qword_180009868, rax
0x180002249  lea     rsi, aSigEndSignatur_1; "<!-- SIG # End signature block -->\r\n"
0x180002250  lea     rax, aPs1xml; "ps1xml"
0x180002257  mov     cs:qword_1800098A0, rbp
0x18000225e  mov     cs:qword_180009890, rax
0x180002265  lea     rdi, aSigEndSignatur_2; "<!-- SIG # End signature block -->"
0x18000226c  lea     rax, aPsc1; "psc1"
0x180002273  mov     cs:qword_1800098A8, rsi
0x18000227a  mov     cs:qword_1800098E0, rax
0x180002281  lea     rbx, asc_1800076E0; "<!-- "
0x180002288  lea     rax, aPsd1; "psd1"
0x18000228f  mov     cs:qword_1800098B0, rdi
0x180002296  mov     cs:qword_180009930, rax
0x18000229d  lea     r11, asc_1800076D0; " -->"
0x1800022a4  lea     rax, aSigBeginSignat; "\r\n# SIG # Begin signature block\r\n"
0x1800022ab  mov     cs:qword_1800098B8, rbx
0x1800022b2  mov     cs:qword_180009938, rax
0x1800022b9  lea     ecx, [rdx-1]
0x1800022bc  lea     rax, aSigBeginSignat_0; "# SIG # Begin signature block"
0x1800022c3  mov     cs:qword_1800098C0, r11
0x1800022ca  mov     cs:qword_180009940, rax
0x1800022d1  lea     rax, aSigEndSignatur; "# SIG # End signature block\r\n"
0x1800022d8  mov     cs:qword_180009948, rax
0x1800022df  lea     rax, aSigEndSignatur_0; "# SIG # End signature block"
0x1800022e6  mov     cs:qword_180009950, rax
0x1800022ed  lea     rax, asc_180007834; "# "
0x1800022f4  mov     cs:qword_180009958, rax
0x1800022fb  lea     rax, aPsm1; "psm1"
0x180002302  mov     cs:qword_180009980, rax
0x180002309  lea     rax, aSigBeginSignat; "\r\n# SIG # Begin signature block\r\n"
0x180002310  mov     cs:qword_180009988, rax
0x180002317  mov     cs:dword_1800098C8, r9d
0x18000231e  mov     cs:dword_1800098CC, r10d
0x180002325  mov     cs:dword_1800098D0, r10d
0x18000232c  mov     cs:dword_1800098D4, r8d
0x180002333  mov     cs:dword_1800098D8, edx
0x180002339  mov     cs:dword_1800098DC, ecx
0x18000233f  mov     cs:qword_1800098E8, r14
0x180002346  mov     cs:qword_1800098F0, rbp
0x18000234d  mov     cs:qword_1800098F8, rsi
0x180002354  mov     cs:qword_180009900, rdi
0x18000235b  mov     cs:qword_180009908, rbx
0x180002362  mov     cs:qword_180009910, r11
0x180002369  mov     cs:dword_180009918, r9d
0x180002370  mov     cs:dword_18000991C, r10d
0x180002377  mov     cs:dword_180009920, r10d
0x18000237e  mov     cs:dword_180009924, r8d
0x180002385  mov     cs:dword_180009928, edx
0x18000238b  mov     cs:dword_18000992C, ecx
0x180002391  mov     cs:qword_180009960, 0
0x18000239c  mov     cs:dword_180009968, 21h ; '!'
0x1800023a6  mov     cs:dword_18000996C, r13d
0x1800023ad  mov     cs:dword_180009970, r13d
0x1800023b4  mov     cs:dword_180009974, 1Bh
0x1800023be  mov     cs:qword_180009978, 2
0x1800023c9  lea     rax, aSigBeginSignat_0; "# SIG # Begin signature block"
0x1800023d0  mov     cs:qword_1800099B0, 0
0x1800023db  mov     cs:qword_180009990, rax
0x1800023e2  lea     rax, aSigEndSignatur; "# SIG # End signature block\r\n"
0x1800023e9  mov     cs:qword_180009998, rax
0x1800023f0  lea     rax, aSigEndSignatur_0; "# SIG # End signature block"
0x1800023f7  mov     cs:qword_1800099A0, rax
0x1800023fe  lea     rax, asc_180007834; "# "
0x180002405  mov     cs:qword_1800099A8, rax
0x18000240c  lea     rax, aCdxml; "cdxml"
0x180002413  mov     cs:qword_1800099D0, rax
0x18000241a  lea     rax, aMof; "mof"
0x180002421  mov     cs:qword_180009A20, rax
0x180002428  lea     rax, aSigBeginSignat_3; "\r\n/* SIG # Begin signature block */\r"...
0x18000242f  mov     cs:qword_180009A28, rax
0x180002436  lea     rax, aSigBeginSignat_4; "/* SIG # Begin signature block */"
0x18000243d  mov     cs:qword_180009A30, rax
0x180002444  lea     rax, aSigEndSignatur_3; "/* SIG # End signature block */\r\n"
0x18000244b  mov     cs:qword_180009A38, rax
0x180002452  lea     rax, aSigEndSignatur_4; "/* SIG # End signature block */"
0x180002459  mov     cs:qword_180009A40, rax
0x180002460  lea     rax, asc_180007598; "/* "
0x180002467  mov     cs:qword_180009A48, rax
0x18000246e  lea     rax, asc_180007590; " */"
0x180002475  mov     cs:qword_180009A50, rax
0x18000247c  lea     eax, [rdx+1Ch]
0x18000247f  mov     cs:dword_180009A5C, eax
0x180002485  mov     cs:dword_180009A60, eax
0x18000248b  lea     eax, [rdx-2]
0x18000248e  mov     cs:dword_180009A68, eax
0x180002494  mov     cs:dword_180009A6C, eax
0x18000249a  mov     cs:dword_1800099B8, 21h ; '!'
0x1800024a4  mov     cs:dword_1800099BC, r13d
0x1800024ab  mov     cs:dword_1800099C0, r13d
0x1800024b2  mov     cs:dword_1800099C4, 1Bh
0x1800024bc  mov     cs:qword_1800099C8, 2
0x1800024c7  mov     cs:qword_1800099D8, r14
0x1800024ce  mov     cs:qword_1800099E0, rbp
0x1800024d5  mov     cs:qword_1800099E8, rsi
0x1800024dc  mov     cs:qword_1800099F0, rdi
0x1800024e3  mov     cs:qword_1800099F8, rbx
0x1800024ea  mov     cs:qword_180009A00, r11
0x1800024f1  mov     cs:dword_180009A08, r9d
0x1800024f8  mov     cs:dword_180009A0C, r10d
0x1800024ff  mov     cs:dword_180009A10, r10d
0x180002506  mov     cs:dword_180009A14, r8d
0x18000250d  mov     cs:dword_180009A18, edx
0x180002513  mov     cs:dword_180009A1C, ecx
0x180002519  mov     cs:dword_180009A58, 25h ; '%'
0x180002523  mov     cs:dword_180009A64, 1Fh
0x18000252d  pop     r14
0x18000252f  pop     r13
0x180002531  pop     rdi
0x180002532  pop     rsi
0x180002533  pop     rbp
0x180002534  pop     rbx
0x180002535  retn
```
