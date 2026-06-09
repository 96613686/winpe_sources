# IDriverLoad

- ea: `0x1800040a0`
- end: `0x18000436f`
- name: `IDriverLoad`
- size: `719`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1800043d0`
- `0x180004b70`
- `0x180005530`

## callees

- `0x1800040a0`
- `0x180004380`
- `0x1800043d0`
- `0x180004470`
- `0x1800045b0`
- `0x1800046f0`
- `0x180004840`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000425f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000425f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004105`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004105`
- `api-ms-win-mm-misc-l1-1-0!OpenDriver` at `0x180004291`
- `api-ms-win-mm-misc-l1-1-0!OpenDriver` at `0x180004291`

## pseudocode

```c

```

## disassembly

```asm
0x1800040a0  push    rbx
0x1800040a2  sub     rsp, 20h
0x1800040a6  mov     rbx, rcx
0x1800040a9  test    rcx, rcx
0x1800040ac  jz      loc_1800042F3
0x1800040b2  mov     ecx, [rcx+38h]
0x1800040b5  mov     [rsp+28h+arg_0], rbp
0x1800040ba  xor     ebp, ebp
0x1800040bc  mov     [rsp+28h+arg_8], rsi
0x1800040c1  test    cl, 1
0x1800040c4  jnz     loc_1800042E1
0x1800040ca  cmp     [rbx+60h], rbp
0x1800040ce  jz      loc_18000427C
0x1800040d4  bt      ecx, 1Ch
0x1800040d8  jnb     loc_1800042FD
0x1800040de  or      dword ptr [rbx+38h], 1
0x1800040e2  test    dword ptr [rbx+38h], 10000000h
0x1800040e9  jnz     loc_1800042E1
0x1800040ef  mov     edx, 70Ch; uBytes
0x1800040f4  mov     [rsp+28h+arg_10], rdi
0x1800040f9  mov     ecx, 40h ; '@'; uFlags
0x1800040fe  mov     dword ptr [rbx+0Ch], 1
0x180004105  call    cs:__imp_LocalAlloc
0x18000410b  mov     rdi, rax
0x18000410e  test    rax, rax
0x180004111  jz      loc_180004352
0x180004117  xor     r8d, r8d
0x18000411a  mov     dword ptr [rax], 70Ch
0x180004120  mov     rdx, rax
0x180004123  mov     rcx, rbx
0x180004126  call    IDriverDetails
0x18000412b  mov     esi, eax
0x18000412d  test    eax, eax
0x18000412f  jnz     loc_18000425C
0x180004135  mov     eax, 500h
0x18000413a  cmp     ax, [rdi+12h]
0x18000413e  jb      loc_180004365
0x180004144  cmp     dword ptr [rdi], 70Ch
0x18000414a  jnz     loc_180004365
0x180004150  cmp     dword ptr [rdi+4], 63647561h
0x180004157  jnz     loc_180004365
0x18000415d  cmp     [rdi+8], ebp
0x180004160  jnz     loc_180004365
0x180004166  lea     rcx, [rdi+2Ch]
0x18000416a  mov     edx, 20h ; ' '
0x18000416f  call    ValidateStringW
0x180004174  test    eax, eax
0x180004176  jz      loc_180004365
0x18000417c  lea     rcx, [rdi+6Ch]
0x180004180  mov     edx, 80h
0x180004185  call    ValidateStringW
0x18000418a  test    eax, eax
0x18000418c  jz      loc_180004365
0x180004192  lea     rcx, [rdi+16Ch]
0x180004199  mov     edx, 50h ; 'P'
0x18000419e  call    ValidateStringW
0x1800041a3  test    eax, eax
0x1800041a5  jz      loc_180004365
0x1800041ab  lea     rcx, [rdi+20Ch]
0x1800041b2  mov     edx, 80h
0x1800041b7  call    ValidateStringW
0x1800041bc  test    eax, eax
0x1800041be  jz      loc_180004365
0x1800041c4  lea     rcx, [rdi+30Ch]
0x1800041cb  mov     edx, 200h
0x1800041d0  call    ValidateStringW
0x1800041d5  test    eax, eax
0x1800041d7  jz      loc_180004365
0x1800041dd  mov     [rbx+0Ch], ebp
0x1800041e0  mov     rcx, rbx
0x1800041e3  mov     eax, [rdi+18h]
0x1800041e6  btr     eax, 1Fh
0x1800041ea  mov     [rbx+3Ch], eax
0x1800041ed  mov     eax, [rdi+1Ch]
0x1800041f0  mov     [rbx+40h], eax
0x1800041f3  call    IDriverGetFormatTags
0x1800041f8  mov     esi, eax
0x1800041fa  test    eax, eax
0x1800041fc  jnz     loc_1800042C5
0x180004202  mov     eax, [rdi+20h]
0x180004205  mov     rcx, rbx
0x180004208  mov     [rbx+4Ch], eax
0x18000420b  call    IDriverGetFilterTags
0x180004210  mov     esi, eax
0x180004212  test    eax, eax
0x180004214  jnz     loc_1800042C5
0x18000421a  xor     r9d, r9d
0x18000421d  xor     r8d, r8d
0x180004220  mov     edx, 8
0x180004225  mov     rcx, rbx
0x180004228  call    IDriverMessageId
0x18000422d  test    rax, rax
0x180004230  jnz     loc_18000435C
0x180004236  xor     r9d, r9d
0x180004239  mov     edx, 600Bh
0x18000423e  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180004245  mov     rcx, rbx
0x180004248  call    IDriverMessageId
0x18000424d  test    rax, rax
0x180004250  jz      short loc_1800042CE
0x180004252  mov     rcx, rbx
0x180004255  call    IDriverWriteRegistryData
0x18000425a  mov     esi, ebp
0x18000425c  mov     rcx, rdi; hMem
0x18000425f  call    cs:__imp_LocalFree
0x180004265  mov     rdi, [rsp+28h+arg_10]
0x18000426a  mov     eax, esi
0x18000426c  mov     rsi, [rsp+28h+arg_8]
0x180004271  mov     rbp, [rsp+28h+arg_0]
0x180004276  add     rsp, 20h
0x18000427a  pop     rbx
0x18000427b  retn
0x18000427c  xor     r8d, r8d; lParam2
0x18000427f  test    dword ptr [rbx+34h], 40000000h
0x180004286  jz      short loc_1800042D7
0x180004288  mov     rcx, [rbx+198h]; szDriverName
0x18000428f  xor     edx, edx; szSectionName
0x180004291  call    cs:__imp_OpenDriver
0x180004297  test    rax, rax
0x18000429a  mov     [rbx+58h], rax
0x18000429e  mov     esi, 6
0x1800042a3  cmovnz  esi, ebp
0x1800042a6  jnz     loc_1800040DE
0x1800042ac  mov     rbp, [rsp+28h+arg_0]
0x1800042b1  mov     eax, esi
0x1800042b3  mov     rsi, [rsp+28h+arg_8]
0x1800042b8  mov     dword ptr [rbx+0Ch], 1
0x1800042bf  add     rsp, 20h
0x1800042c3  pop     rbx
0x1800042c4  retn
0x1800042c5  mov     dword ptr [rbx+0Ch], 1
0x1800042cc  jmp     short loc_18000425C
0x1800042ce  or      dword ptr [rbx+38h], 4
0x1800042d2  jmp     loc_180004252
0x1800042d7  mov     rdx, [rbx+70h]
0x1800042db  lea     rcx, [rbx+78h]
0x1800042df  jmp     short loc_180004291
0x1800042e1  mov     rsi, [rsp+28h+arg_8]
0x1800042e6  mov     eax, ebp
0x1800042e8  mov     rbp, [rsp+28h+arg_0]
0x1800042ed  add     rsp, 20h
0x1800042f1  pop     rbx
0x1800042f2  retn
0x1800042f3  mov     eax, 5
0x1800042f8  jmp     loc_180004276
0x1800042fd  xor     r9d, r9d
0x180004300  xor     r8d, r8d
0x180004303  mov     edx, 1
0x180004308  mov     rcx, rbx
0x18000430b  call    IDriverMessageId
0x180004310  test    rax, rax
0x180004313  jz      short loc_180004348
0x180004315  xor     r9d, r9d
0x180004318  xor     r8d, r8d
0x18000431b  mov     edx, 2
0x180004320  mov     rcx, rbx
0x180004323  call    IDriverMessageId
0x180004328  xor     r9d, r9d
0x18000432b  xor     r8d, r8d
0x18000432e  mov     edx, 3
0x180004333  mov     rcx, rbx
0x180004336  call    IDriverMessageId
0x18000433b  mov     [rbx+68h], rax
0x18000433f  test    rax, rax
0x180004342  jnz     loc_1800040DE
0x180004348  mov     esi, 6
0x18000434d  jmp     loc_1800042AC
0x180004352  mov     esi, 7
0x180004357  jmp     loc_180004265
0x18000435c  or      dword ptr [rbx+38h], 2
0x180004360  jmp     loc_180004236
0x180004365  mov     esi, 1
0x18000436a  jmp     loc_18000425C
```
