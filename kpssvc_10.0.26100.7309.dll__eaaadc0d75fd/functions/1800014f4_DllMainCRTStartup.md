# __DllMainCRTStartup

- ea: `0x1800014f4`
- end: `0x180001701`
- name: `__DllMainCRTStartup`
- size: `525`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800014b0`

## callees

- `0x18000126c`
- `0x1800014f4`
- `0x1800017dc`
- `0x1800019c4`
- `0x180032010`

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
  if ( (_DWORD)fdwReason || dword_18003A3C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18003A3C4 = 1;
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
            if ( dword_18003A3C4 )
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
0x1800014f4  mov     [rsp+lpvReserved], r8
0x1800014f9  mov     [rsp+arg_8], edx
0x1800014fd  mov     [rsp+arg_0], rcx
0x180001502  push    rbx
0x180001503  push    rsi
0x180001504  push    rdi
0x180001505  sub     rsp, 150h
0x18000150c  mov     edi, edx
0x18000150e  mov     rsi, rcx
0x180001511  mov     ebx, 1
0x180001516  mov     [rsp+168h+var_148], ebx
0x18000151a  cmp     edx, ebx
0x18000151c  ja      short loc_180001524
0x18000151e  mov     cs:__native_dllmain_reason, edx
0x180001524  test    edx, edx
0x180001526  jnz     short loc_18000153B
0x180001528  cmp     cs:dword_18003A3C0, edx
0x18000152e  jnz     short loc_18000153B
0x180001530  xor     ebx, ebx
0x180001532  mov     [rsp+168h+var_148], ebx
0x180001536  jmp     loc_1800016E5
0x18000153b  lea     eax, [rdx-1]
0x18000153e  cmp     eax, 1
0x180001541  ja      loc_1800015C7
0x180001547  mov     rax, cs:_pRawDllMain
0x18000154e  test    rax, rax
0x180001551  jz      short loc_180001588
0x180001553  cmp     edx, 1
0x180001556  jnz     short loc_18000155E
0x180001558  mov     cs:dword_18003A3C4, edx
0x18000155e  mov     r8, [rsp+168h+lpvReserved]
0x180001566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000156b  mov     ebx, eax
0x18000156d  mov     [rsp+168h+var_148], eax
0x180001571  jmp     short loc_180001588
0x180001573  xor     ebx, ebx
0x180001575  mov     [rsp+168h+var_148], ebx
0x180001579  mov     edi, [rsp+168h+arg_8]
0x180001580  mov     rsi, [rsp+168h+arg_0]
0x180001588  test    ebx, ebx
0x18000158a  jz      loc_1800016E5
0x180001590  mov     r8, [rsp+168h+lpvReserved]
0x180001598  mov     edx, edi
0x18000159a  mov     rcx, rsi
0x18000159d  call    _CRT_INIT
0x1800015a2  mov     ebx, eax
0x1800015a4  mov     [rsp+168h+var_148], eax
0x1800015a8  jmp     short loc_1800015BF
0x1800015aa  xor     ebx, ebx
0x1800015ac  mov     [rsp+168h+var_148], ebx
0x1800015b0  mov     edi, [rsp+168h+arg_8]
0x1800015b7  mov     rsi, [rsp+168h+arg_0]
0x1800015bf  test    ebx, ebx
0x1800015c1  jz      loc_1800016E5
0x1800015c7  mov     r8, [rsp+168h+lpvReserved]; lpvReserved
0x1800015cf  mov     edx, edi; fdwReason
0x1800015d1  mov     rcx, rsi; hinstDLL
0x1800015d4  call    DllMain
0x1800015d9  mov     ebx, eax
0x1800015db  mov     [rsp+168h+var_148], eax
0x1800015df  jmp     short loc_1800015F6
0x1800015e1  xor     ebx, ebx
0x1800015e3  mov     [rsp+168h+var_148], ebx
0x1800015e7  mov     edi, [rsp+168h+arg_8]
0x1800015ee  mov     rsi, [rsp+168h+arg_0]
0x1800015f6  cmp     edi, 1
0x1800015f9  jnz     short loc_180001671
0x1800015fb  test    ebx, ebx
0x1800015fd  jnz     short loc_180001671
0x1800015ff  xor     r8d, r8d; lpvReserved
0x180001602  xor     edx, edx; fdwReason
0x180001604  mov     rcx, rsi; hinstDLL
0x180001607  call    DllMain
0x18000160c  jmp     short loc_180001621
0x18000160e  mov     edi, [rsp+168h+arg_8]
0x180001615  mov     rsi, [rsp+168h+arg_0]
0x18000161d  mov     ebx, [rsp+168h+var_148]
0x180001621  xor     r8d, r8d
0x180001624  xor     edx, edx
0x180001626  mov     rcx, rsi
0x180001629  call    _CRT_INIT
0x18000162e  jmp     short loc_180001643
0x180001630  mov     edi, [rsp+168h+arg_8]
0x180001637  mov     rsi, [rsp+168h+arg_0]
0x18000163f  mov     ebx, [rsp+168h+var_148]
0x180001643  mov     rax, cs:_pRawDllMain
0x18000164a  test    rax, rax
0x18000164d  jz      short loc_180001671
0x18000164f  xor     r8d, r8d
0x180001652  xor     edx, edx
0x180001654  mov     rcx, rsi
0x180001657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000165c  jmp     short loc_180001671
0x18000165e  mov     edi, [rsp+168h+arg_8]
0x180001665  mov     rsi, [rsp+168h+arg_0]
0x18000166d  mov     ebx, [rsp+168h+var_148]
0x180001671  test    edi, edi
0x180001673  jz      short loc_18000167A
0x180001675  cmp     edi, 3
0x180001678  jnz     short loc_1800016E5
0x18000167a  mov     r8, [rsp+168h+lpvReserved]
0x180001682  mov     edx, edi
0x180001684  mov     rcx, rsi
0x180001687  call    _CRT_INIT
0x18000168c  mov     ebx, eax
0x18000168e  mov     [rsp+168h+var_148], eax
0x180001692  jmp     short loc_1800016A9
0x180001694  xor     ebx, ebx
0x180001696  mov     [rsp+168h+var_148], ebx
0x18000169a  mov     edi, [rsp+168h+arg_8]
0x1800016a1  mov     rsi, [rsp+168h+arg_0]
0x1800016a9  mov     rax, cs:_pRawDllMain
0x1800016b0  test    rax, rax
0x1800016b3  jz      short loc_1800016E5
0x1800016b5  cmp     cs:dword_18003A3C4, 0
0x1800016bc  jz      short loc_1800016E5
0x1800016be  mov     r8, [rsp+168h+lpvReserved]
0x1800016c6  mov     edx, edi
0x1800016c8  mov     rcx, rsi
0x1800016cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016d0  mov     ebx, eax
0x1800016d2  mov     [rsp+168h+var_148], eax
0x1800016d6  jmp     short loc_1800016E5
0x1800016d8  xor     ebx, ebx
0x1800016da  mov     [rsp+168h+var_148], ebx
0x1800016de  mov     edi, [rsp+168h+arg_8]
0x1800016e5  cmp     edi, 1
0x1800016e8  ja      short loc_1800016F4
0x1800016ea  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800016f4  mov     eax, ebx
0x1800016f6  add     rsp, 150h
0x1800016fd  pop     rdi
0x1800016fe  pop     rsi
0x1800016ff  pop     rbx
0x180001700  retn
0x180031153  push    rbp
0x180031155  sub     rsp, 20h
0x180031159  mov     rbp, rdx
0x18003115c  mov     [rbp+108h], rcx
0x180031163  mov     rax, [rcx]
0x180031166  mov     edx, [rax]
0x180031168  mov     [rbp+0A4h], edx
0x18003116e  mov     [rbp+0C8h], rcx
0x180031175  mov     [rbp+28h], edx
0x180031178  mov     eax, [rbp+28h]
0x18003117b  cmp     eax, 0E06D7363h
0x180031180  jnz     short loc_180031196
0x180031182  mov     rdx, [rbp+0C8h]
0x180031189  mov     ecx, [rbp+28h]
0x18003118c  call    _XcptFilter_0
0x180031191  mov     [rbp+30h], eax
0x180031194  jmp     short loc_18003119D
0x180031196  mov     dword ptr [rbp+30h], 0
0x18003119d  mov     eax, [rbp+30h]
0x1800311a0  add     rsp, 20h
0x1800311a4  pop     rbp
0x1800311a5  retn
0x1800311a7  push    rbp
0x1800311a9  sub     rsp, 20h
0x1800311ad  mov     rbp, rdx
0x1800311b0  mov     [rbp+110h], rcx
0x1800311b7  mov     rax, [rcx]
0x1800311ba  mov     edx, [rax]
0x1800311bc  mov     [rbp+0A8h], edx
0x1800311c2  mov     [rbp+0D0h], rcx
0x1800311c9  mov     [rbp+38h], edx
0x1800311cc  mov     eax, [rbp+38h]
0x1800311cf  cmp     eax, 0E06D7363h
0x1800311d4  jnz     short loc_1800311EA
0x1800311d6  mov     rdx, [rbp+0D0h]
0x1800311dd  mov     ecx, [rbp+38h]
0x1800311e0  call    _XcptFilter_0
0x1800311e5  mov     [rbp+40h], eax
0x1800311e8  jmp     short loc_1800311F1
0x1800311ea  mov     dword ptr [rbp+40h], 0
0x1800311f1  mov     eax, [rbp+40h]
0x1800311f4  add     rsp, 20h
0x1800311f8  pop     rbp
0x1800311f9  retn
0x1800311fb  push    rbp
0x1800311fd  sub     rsp, 20h
0x180031201  mov     rbp, rdx
0x180031204  mov     [rbp+118h], rcx
0x18003120b  mov     rax, [rcx]
0x18003120e  mov     edx, [rax]
0x180031210  mov     [rbp+0ACh], edx
0x180031216  mov     [rbp+0D8h], rcx
0x18003121d  mov     [rbp+48h], edx
0x180031220  mov     eax, [rbp+48h]
0x180031223  cmp     eax, 0E06D7363h
0x180031228  jnz     short loc_18003123E
0x18003122a  mov     rdx, [rbp+0D8h]
0x180031231  mov     ecx, [rbp+48h]
0x180031234  call    _XcptFilter_0
0x180031239  mov     [rbp+50h], eax
0x18003123c  jmp     short loc_180031245
0x18003123e  mov     dword ptr [rbp+50h], 0
0x180031245  mov     eax, [rbp+50h]
0x180031248  add     rsp, 20h
0x18003124c  pop     rbp
0x18003124d  retn
0x18003124f  push    rbp
0x180031251  sub     rsp, 20h
0x180031255  mov     rbp, rdx
0x180031258  mov     [rbp+120h], rcx
0x18003125f  mov     rax, [rcx]
0x180031262  mov     edx, [rax]
0x180031264  mov     [rbp+0B0h], edx
0x18003126a  mov     [rbp+0E0h], rcx
0x180031271  mov     [rbp+58h], edx
0x180031274  mov     eax, [rbp+58h]
0x180031277  cmp     eax, 0E06D7363h
0x18003127c  jnz     short loc_180031292
0x18003127e  mov     rdx, [rbp+0E0h]
0x180031285  mov     ecx, [rbp+58h]
0x180031288  call    _XcptFilter_0
0x18003128d  mov     [rbp+60h], eax
0x180031290  jmp     short loc_180031299
0x180031292  mov     dword ptr [rbp+60h], 0
0x180031299  mov     eax, [rbp+60h]
0x18003129c  add     rsp, 20h
0x1800312a0  pop     rbp
0x1800312a1  retn
0x1800312a3  push    rbp
0x1800312a5  sub     rsp, 20h
0x1800312a9  mov     rbp, rdx
0x1800312ac  mov     [rbp+128h], rcx
0x1800312b3  mov     rax, [rcx]
0x1800312b6  mov     edx, [rax]
0x1800312b8  mov     [rbp+0B4h], edx
0x1800312be  mov     [rbp+0E8h], rcx
0x1800312c5  mov     [rbp+68h], edx
0x1800312c8  mov     eax, [rbp+68h]
0x1800312cb  cmp     eax, 0E06D7363h
0x1800312d0  jnz     short loc_1800312E6
0x1800312d2  mov     rdx, [rbp+0E8h]
0x1800312d9  mov     ecx, [rbp+68h]
0x1800312dc  call    _XcptFilter_0
0x1800312e1  mov     [rbp+70h], eax
0x1800312e4  jmp     short loc_1800312ED
0x1800312e6  mov     dword ptr [rbp+70h], 0
0x1800312ed  mov     eax, [rbp+70h]
0x1800312f0  add     rsp, 20h
0x1800312f4  pop     rbp
0x1800312f5  retn
0x1800312f7  push    rbp
0x1800312f9  sub     rsp, 20h
0x1800312fd  mov     rbp, rdx
0x180031300  mov     [rbp+130h], rcx
0x180031307  mov     rax, [rcx]
0x18003130a  mov     edx, [rax]
0x18003130c  mov     [rbp+0B8h], edx
0x180031312  mov     [rbp+0F0h], rcx
0x180031319  mov     [rbp+78h], edx
0x18003131c  mov     eax, [rbp+78h]
0x18003131f  cmp     eax, 0E06D7363h
0x180031324  jnz     short loc_18003133D
0x180031326  mov     rdx, [rbp+0F0h]
0x18003132d  mov     ecx, [rbp+78h]
0x180031330  call    _XcptFilter_0
0x180031335  mov     [rbp+80h], eax
0x18003133b  jmp     short loc_180031347
0x18003133d  mov     dword ptr [rbp+80h], 0
0x180031347  mov     eax, [rbp+80h]
0x18003134d  add     rsp, 20h
0x180031351  pop     rbp
0x180031352  retn
0x180031354  push    rbp
0x180031356  sub     rsp, 20h
0x18003135a  mov     rbp, rdx
0x18003135d  mov     [rbp+138h], rcx
0x180031364  mov     rax, [rcx]
0x180031367  mov     edx, [rax]
0x180031369  mov     [rbp+0BCh], edx
0x18003136f  mov     [rbp+0F8h], rcx
0x180031376  mov     [rbp+88h], edx
0x18003137c  mov     eax, [rbp+88h]
0x180031382  cmp     eax, 0E06D7363h
0x180031387  jnz     short loc_1800313A3
0x180031389  mov     rdx, [rbp+0F8h]
0x180031390  mov     ecx, [rbp+88h]
0x180031396  call    _XcptFilter_0
0x18003139b  mov     [rbp+90h], eax
0x1800313a1  jmp     short loc_1800313AD
0x1800313a3  mov     dword ptr [rbp+90h], 0
0x1800313ad  mov     eax, [rbp+90h]
0x1800313b3  add     rsp, 20h
0x1800313b7  pop     rbp
0x1800313b8  retn
0x1800313ba  push    rbp
0x1800313bc  sub     rsp, 20h
0x1800313c0  mov     rbp, rdx
0x1800313c3  mov     [rbp+140h], rcx
0x1800313ca  mov     rax, [rcx]
0x1800313cd  mov     edx, [rax]
0x1800313cf  mov     [rbp+0C0h], edx
0x1800313d5  mov     [rbp+100h], rcx
0x1800313dc  mov     [rbp+98h], edx
0x1800313e2  mov     eax, [rbp+98h]
0x1800313e8  cmp     eax, 0E06D7363h
  ... truncated ...
```
