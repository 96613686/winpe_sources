# __DllMainCRTStartup

- ea: `0x180001564`
- end: `0x180001770`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001520`

## callees

- `0x180001090`
- `0x1800012f0`
- `0x180001564`
- `0x180001879`
- `0x180003080`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_1800071A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800071A4 = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_1800071A4 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x180001564  mov     [rsp+lpvReserved], r8
0x180001569  mov     [rsp+arg_8], edx
0x18000156d  mov     [rsp+arg_0], rcx
0x180001572  push    rbx
0x180001573  push    rsi
0x180001574  push    rdi
0x180001575  sub     rsp, 0F0h
0x18000157c  mov     edi, edx
0x18000157e  mov     rsi, rcx
0x180001581  mov     ebx, 1
0x180001586  cmp     edx, ebx
0x180001588  ja      short loc_180001590
0x18000158a  mov     cs:__native_dllmain_reason, edx
0x180001590  test    edx, edx
0x180001592  jnz     short loc_1800015A7
0x180001594  cmp     cs:dword_1800071A0, edx
0x18000159a  jnz     short loc_1800015A7
0x18000159c  xor     ebx, ebx
0x18000159e  mov     [rsp+108h+var_E8], ebx
0x1800015a2  jmp     loc_180001754
0x1800015a7  lea     eax, [rdx-1]
0x1800015aa  cmp     eax, 1
0x1800015ad  ja      loc_180001634
0x1800015b3  mov     rax, cs:_pRawDllMain
0x1800015ba  test    rax, rax
0x1800015bd  jz      short loc_1800015F5
0x1800015bf  cmp     edx, 1
0x1800015c2  jnz     short loc_1800015CA
0x1800015c4  mov     cs:dword_1800071A4, edx
0x1800015ca  mov     r8, [rsp+108h+lpvReserved]
0x1800015d2  call    cs:__guard_dispatch_icall_fptr
0x1800015d8  mov     ebx, eax
0x1800015da  mov     [rsp+108h+var_E8], eax
0x1800015de  jmp     short loc_1800015F5
0x1800015e0  xor     ebx, ebx
0x1800015e2  mov     [rsp+108h+var_E8], ebx
0x1800015e6  mov     edi, [rsp+108h+arg_8]
0x1800015ed  mov     rsi, [rsp+108h+arg_0]
0x1800015f5  test    ebx, ebx
0x1800015f7  jz      loc_180001754
0x1800015fd  mov     r8, [rsp+108h+lpvReserved]
0x180001605  mov     edx, edi
0x180001607  mov     rcx, rsi
0x18000160a  call    _CRT_INIT
0x18000160f  mov     ebx, eax
0x180001611  mov     [rsp+108h+var_E8], eax
0x180001615  jmp     short loc_18000162C
0x180001617  xor     ebx, ebx
0x180001619  mov     [rsp+108h+var_E8], ebx
0x18000161d  mov     edi, [rsp+108h+arg_8]
0x180001624  mov     rsi, [rsp+108h+arg_0]
0x18000162c  test    ebx, ebx
0x18000162e  jz      loc_180001754
0x180001634  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000163c  mov     edx, edi; fdwReason
0x18000163e  mov     rcx, rsi; hinstDLL
0x180001641  call    DllMain
0x180001646  mov     ebx, eax
0x180001648  mov     [rsp+108h+var_E8], eax
0x18000164c  jmp     short loc_180001663
0x18000164e  xor     ebx, ebx
0x180001650  mov     [rsp+108h+var_E8], ebx
0x180001654  mov     edi, [rsp+108h+arg_8]
0x18000165b  mov     rsi, [rsp+108h+arg_0]
0x180001663  cmp     edi, 1
0x180001666  jnz     short loc_1800016DF
0x180001668  test    ebx, ebx
0x18000166a  jnz     short loc_1800016DF
0x18000166c  xor     r8d, r8d; lpvReserved
0x18000166f  xor     edx, edx; fdwReason
0x180001671  mov     rcx, rsi; hinstDLL
0x180001674  call    DllMain
0x180001679  jmp     short loc_18000168E
0x18000167b  mov     edi, [rsp+108h+arg_8]
0x180001682  mov     rsi, [rsp+108h+arg_0]
0x18000168a  mov     ebx, [rsp+108h+var_E8]
0x18000168e  xor     r8d, r8d
0x180001691  xor     edx, edx
0x180001693  mov     rcx, rsi
0x180001696  call    _CRT_INIT
0x18000169b  jmp     short loc_1800016B0
0x18000169d  mov     edi, [rsp+108h+arg_8]
0x1800016a4  mov     rsi, [rsp+108h+arg_0]
0x1800016ac  mov     ebx, [rsp+108h+var_E8]
0x1800016b0  mov     rax, cs:_pRawDllMain
0x1800016b7  test    rax, rax
0x1800016ba  jz      short loc_1800016DF
0x1800016bc  xor     r8d, r8d
0x1800016bf  xor     edx, edx
0x1800016c1  mov     rcx, rsi
0x1800016c4  call    cs:__guard_dispatch_icall_fptr
0x1800016ca  jmp     short loc_1800016DF
0x1800016cc  mov     edi, [rsp+108h+arg_8]
0x1800016d3  mov     rsi, [rsp+108h+arg_0]
0x1800016db  mov     ebx, [rsp+108h+var_E8]
0x1800016df  test    edi, edi
0x1800016e1  jz      short loc_1800016E8
0x1800016e3  cmp     edi, 3
0x1800016e6  jnz     short loc_180001754
0x1800016e8  mov     r8, [rsp+108h+lpvReserved]
0x1800016f0  mov     edx, edi
0x1800016f2  mov     rcx, rsi
0x1800016f5  call    _CRT_INIT
0x1800016fa  mov     ebx, eax
0x1800016fc  mov     [rsp+108h+var_E8], eax
0x180001700  jmp     short loc_180001717
0x180001702  xor     ebx, ebx
0x180001704  mov     [rsp+108h+var_E8], ebx
0x180001708  mov     edi, [rsp+108h+arg_8]
0x18000170f  mov     rsi, [rsp+108h+arg_0]
0x180001717  mov     rax, cs:_pRawDllMain
0x18000171e  test    rax, rax
0x180001721  jz      short loc_180001754
0x180001723  cmp     cs:dword_1800071A4, 0
0x18000172a  jz      short loc_180001754
0x18000172c  mov     r8, [rsp+108h+lpvReserved]
0x180001734  mov     edx, edi
0x180001736  mov     rcx, rsi
0x180001739  call    cs:__guard_dispatch_icall_fptr
0x18000173f  mov     ebx, eax
0x180001741  mov     [rsp+108h+var_E8], eax
0x180001745  jmp     short loc_180001754
0x180001747  xor     ebx, ebx
0x180001749  mov     [rsp+108h+var_E8], ebx
0x18000174d  mov     edi, [rsp+108h+arg_8]
0x180001754  cmp     edi, 1
0x180001757  ja      short loc_180001763
0x180001759  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001763  mov     eax, ebx
0x180001765  add     rsp, 0F0h
0x18000176c  pop     rdi
0x18000176d  pop     rsi
0x18000176e  pop     rbx
0x18000176f  retn
0x180003116  push    rbp
0x180003118  sub     rsp, 20h
0x18000311c  mov     rbp, rdx
0x18000311f  mov     rax, [rcx]
0x180003122  mov     edx, [rax]
0x180003124  mov     [rbp+0A8h], rcx
0x18000312b  mov     [rbp+28h], edx
0x18000312e  mov     eax, [rbp+28h]
0x180003131  cmp     eax, 0E06D7363h
0x180003136  jnz     short loc_18000314C
0x180003138  mov     rdx, [rbp+0A8h]
0x18000313f  mov     ecx, [rbp+28h]
0x180003142  call    _XcptFilter_0
0x180003147  mov     [rbp+30h], eax
0x18000314a  jmp     short loc_180003153
0x18000314c  mov     dword ptr [rbp+30h], 0
0x180003153  mov     eax, [rbp+30h]
0x180003156  add     rsp, 20h
0x18000315a  pop     rbp
0x18000315b  retn
0x18000315d  push    rbp
0x18000315f  sub     rsp, 20h
0x180003163  mov     rbp, rdx
0x180003166  mov     rax, [rcx]
0x180003169  mov     edx, [rax]
0x18000316b  mov     [rbp+0B0h], rcx
0x180003172  mov     [rbp+38h], edx
0x180003175  mov     eax, [rbp+38h]
0x180003178  cmp     eax, 0E06D7363h
0x18000317d  jnz     short loc_180003193
0x18000317f  mov     rdx, [rbp+0B0h]
0x180003186  mov     ecx, [rbp+38h]
0x180003189  call    _XcptFilter_0
0x18000318e  mov     [rbp+40h], eax
0x180003191  jmp     short loc_18000319A
0x180003193  mov     dword ptr [rbp+40h], 0
0x18000319a  mov     eax, [rbp+40h]
0x18000319d  add     rsp, 20h
0x1800031a1  pop     rbp
0x1800031a2  retn
0x1800031a4  push    rbp
0x1800031a6  sub     rsp, 20h
0x1800031aa  mov     rbp, rdx
0x1800031ad  mov     rax, [rcx]
0x1800031b0  mov     edx, [rax]
0x1800031b2  mov     [rbp+0B8h], rcx
0x1800031b9  mov     [rbp+48h], edx
0x1800031bc  mov     eax, [rbp+48h]
0x1800031bf  cmp     eax, 0E06D7363h
0x1800031c4  jnz     short loc_1800031DA
0x1800031c6  mov     rdx, [rbp+0B8h]
0x1800031cd  mov     ecx, [rbp+48h]
0x1800031d0  call    _XcptFilter_0
0x1800031d5  mov     [rbp+50h], eax
0x1800031d8  jmp     short loc_1800031E1
0x1800031da  mov     dword ptr [rbp+50h], 0
0x1800031e1  mov     eax, [rbp+50h]
0x1800031e4  add     rsp, 20h
0x1800031e8  pop     rbp
0x1800031e9  retn
0x1800031eb  push    rbp
0x1800031ed  sub     rsp, 20h
0x1800031f1  mov     rbp, rdx
0x1800031f4  mov     rax, [rcx]
0x1800031f7  mov     edx, [rax]
0x1800031f9  mov     [rbp+0C0h], rcx
0x180003200  mov     [rbp+58h], edx
0x180003203  mov     eax, [rbp+58h]
0x180003206  cmp     eax, 0E06D7363h
0x18000320b  jnz     short loc_180003221
0x18000320d  mov     rdx, [rbp+0C0h]
0x180003214  mov     ecx, [rbp+58h]
0x180003217  call    _XcptFilter_0
0x18000321c  mov     [rbp+60h], eax
0x18000321f  jmp     short loc_180003228
0x180003221  mov     dword ptr [rbp+60h], 0
0x180003228  mov     eax, [rbp+60h]
0x18000322b  add     rsp, 20h
0x18000322f  pop     rbp
0x180003230  retn
0x180003232  push    rbp
0x180003234  sub     rsp, 20h
0x180003238  mov     rbp, rdx
0x18000323b  mov     rax, [rcx]
0x18000323e  mov     edx, [rax]
0x180003240  mov     [rbp+0C8h], rcx
0x180003247  mov     [rbp+68h], edx
0x18000324a  mov     eax, [rbp+68h]
0x18000324d  cmp     eax, 0E06D7363h
0x180003252  jnz     short loc_180003268
0x180003254  mov     rdx, [rbp+0C8h]
0x18000325b  mov     ecx, [rbp+68h]
0x18000325e  call    _XcptFilter_0
0x180003263  mov     [rbp+70h], eax
0x180003266  jmp     short loc_18000326F
0x180003268  mov     dword ptr [rbp+70h], 0
0x18000326f  mov     eax, [rbp+70h]
0x180003272  add     rsp, 20h
0x180003276  pop     rbp
0x180003277  retn
0x180003279  push    rbp
0x18000327b  sub     rsp, 20h
0x18000327f  mov     rbp, rdx
0x180003282  mov     rax, [rcx]
0x180003285  mov     edx, [rax]
0x180003287  mov     [rbp+0D0h], rcx
0x18000328e  mov     [rbp+78h], edx
0x180003291  mov     eax, [rbp+78h]
0x180003294  cmp     eax, 0E06D7363h
0x180003299  jnz     short loc_1800032B2
0x18000329b  mov     rdx, [rbp+0D0h]
0x1800032a2  mov     ecx, [rbp+78h]
0x1800032a5  call    _XcptFilter_0
0x1800032aa  mov     [rbp+80h], eax
0x1800032b0  jmp     short loc_1800032BC
0x1800032b2  mov     dword ptr [rbp+80h], 0
0x1800032bc  mov     eax, [rbp+80h]
0x1800032c2  add     rsp, 20h
0x1800032c6  pop     rbp
0x1800032c7  retn
0x1800032c9  push    rbp
0x1800032cb  sub     rsp, 20h
0x1800032cf  mov     rbp, rdx
0x1800032d2  mov     rax, [rcx]
0x1800032d5  mov     edx, [rax]
0x1800032d7  mov     [rbp+0D8h], rcx
0x1800032de  mov     [rbp+88h], edx
0x1800032e4  mov     eax, [rbp+88h]
0x1800032ea  cmp     eax, 0E06D7363h
0x1800032ef  jnz     short loc_18000330B
0x1800032f1  mov     rdx, [rbp+0D8h]
0x1800032f8  mov     ecx, [rbp+88h]
0x1800032fe  call    _XcptFilter_0
0x180003303  mov     [rbp+90h], eax
0x180003309  jmp     short loc_180003315
0x18000330b  mov     dword ptr [rbp+90h], 0
0x180003315  mov     eax, [rbp+90h]
0x18000331b  add     rsp, 20h
0x18000331f  pop     rbp
0x180003320  retn
0x180003322  push    rbp
0x180003324  sub     rsp, 20h
0x180003328  mov     rbp, rdx
0x18000332b  mov     rax, [rcx]
0x18000332e  mov     edx, [rax]
0x180003330  mov     [rbp+0E0h], rcx
0x180003337  mov     [rbp+98h], edx
0x18000333d  mov     eax, [rbp+98h]
0x180003343  cmp     eax, 0E06D7363h
0x180003348  jnz     short loc_180003364
0x18000334a  mov     rdx, [rbp+0E0h]
0x180003351  mov     ecx, [rbp+98h]
0x180003357  call    _XcptFilter_0
0x18000335c  mov     [rbp+0A0h], eax
0x180003362  jmp     short loc_18000336E
0x180003364  mov     dword ptr [rbp+0A0h], 0
0x18000336e  mov     eax, [rbp+0A0h]
0x180003374  add     rsp, 20h
0x180003378  pop     rbp
0x180003379  retn
0x18000337b  push    rbp
0x18000337d  sub     rsp, 20h
0x180003381  mov     rbp, rdx
0x180003384  cmp     dword ptr [rbp+118h], 1
0x18000338b  ja      short loc_180003397
0x18000338d  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
