# __DllMainCRTStartup

- ea: `0x180001654`
- end: `0x180001860`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001610`

## callees

- `0x1800013e0`
- `0x180001654`
- `0x180001d05`
- `0x18000b8f0`
- `0x180018540`

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
  if ( (_DWORD)fdwReason || dword_180021560 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180021564 = 1;
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
            if ( dword_180021564 )
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
0x180001654  mov     [rsp+lpvReserved], r8
0x180001659  mov     [rsp+arg_8], edx
0x18000165d  mov     [rsp+arg_0], rcx
0x180001662  push    rbx
0x180001663  push    rsi
0x180001664  push    rdi
0x180001665  sub     rsp, 0F0h
0x18000166c  mov     edi, edx
0x18000166e  mov     rsi, rcx
0x180001671  mov     ebx, 1
0x180001676  cmp     edx, ebx
0x180001678  ja      short loc_180001680
0x18000167a  mov     cs:__native_dllmain_reason, edx
0x180001680  test    edx, edx
0x180001682  jnz     short loc_180001697
0x180001684  cmp     cs:dword_180021560, edx
0x18000168a  jnz     short loc_180001697
0x18000168c  xor     ebx, ebx
0x18000168e  mov     [rsp+108h+var_E8], ebx
0x180001692  jmp     loc_180001844
0x180001697  lea     eax, [rdx-1]
0x18000169a  cmp     eax, 1
0x18000169d  ja      loc_180001724
0x1800016a3  mov     rax, cs:_pRawDllMain
0x1800016aa  test    rax, rax
0x1800016ad  jz      short loc_1800016E5
0x1800016af  cmp     edx, 1
0x1800016b2  jnz     short loc_1800016BA
0x1800016b4  mov     cs:dword_180021564, edx
0x1800016ba  mov     r8, [rsp+108h+lpvReserved]
0x1800016c2  call    cs:__guard_dispatch_icall_fptr
0x1800016c8  mov     ebx, eax
0x1800016ca  mov     [rsp+108h+var_E8], eax
0x1800016ce  jmp     short loc_1800016E5
0x1800016d0  xor     ebx, ebx
0x1800016d2  mov     [rsp+108h+var_E8], ebx
0x1800016d6  mov     edi, [rsp+108h+arg_8]
0x1800016dd  mov     rsi, [rsp+108h+arg_0]
0x1800016e5  test    ebx, ebx
0x1800016e7  jz      loc_180001844
0x1800016ed  mov     r8, [rsp+108h+lpvReserved]
0x1800016f5  mov     edx, edi
0x1800016f7  mov     rcx, rsi
0x1800016fa  call    _CRT_INIT
0x1800016ff  mov     ebx, eax
0x180001701  mov     [rsp+108h+var_E8], eax
0x180001705  jmp     short loc_18000171C
0x180001707  xor     ebx, ebx
0x180001709  mov     [rsp+108h+var_E8], ebx
0x18000170d  mov     edi, [rsp+108h+arg_8]
0x180001714  mov     rsi, [rsp+108h+arg_0]
0x18000171c  test    ebx, ebx
0x18000171e  jz      loc_180001844
0x180001724  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000172c  mov     edx, edi; fdwReason
0x18000172e  mov     rcx, rsi; hinstDLL
0x180001731  call    DllMain
0x180001736  mov     ebx, eax
0x180001738  mov     [rsp+108h+var_E8], eax
0x18000173c  jmp     short loc_180001753
0x18000173e  xor     ebx, ebx
0x180001740  mov     [rsp+108h+var_E8], ebx
0x180001744  mov     edi, [rsp+108h+arg_8]
0x18000174b  mov     rsi, [rsp+108h+arg_0]
0x180001753  cmp     edi, 1
0x180001756  jnz     short loc_1800017CF
0x180001758  test    ebx, ebx
0x18000175a  jnz     short loc_1800017CF
0x18000175c  xor     r8d, r8d; lpvReserved
0x18000175f  xor     edx, edx; fdwReason
0x180001761  mov     rcx, rsi; hinstDLL
0x180001764  call    DllMain
0x180001769  jmp     short loc_18000177E
0x18000176b  mov     edi, [rsp+108h+arg_8]
0x180001772  mov     rsi, [rsp+108h+arg_0]
0x18000177a  mov     ebx, [rsp+108h+var_E8]
0x18000177e  xor     r8d, r8d
0x180001781  xor     edx, edx
0x180001783  mov     rcx, rsi
0x180001786  call    _CRT_INIT
0x18000178b  jmp     short loc_1800017A0
0x18000178d  mov     edi, [rsp+108h+arg_8]
0x180001794  mov     rsi, [rsp+108h+arg_0]
0x18000179c  mov     ebx, [rsp+108h+var_E8]
0x1800017a0  mov     rax, cs:_pRawDllMain
0x1800017a7  test    rax, rax
0x1800017aa  jz      short loc_1800017CF
0x1800017ac  xor     r8d, r8d
0x1800017af  xor     edx, edx
0x1800017b1  mov     rcx, rsi
0x1800017b4  call    cs:__guard_dispatch_icall_fptr
0x1800017ba  jmp     short loc_1800017CF
0x1800017bc  mov     edi, [rsp+108h+arg_8]
0x1800017c3  mov     rsi, [rsp+108h+arg_0]
0x1800017cb  mov     ebx, [rsp+108h+var_E8]
0x1800017cf  test    edi, edi
0x1800017d1  jz      short loc_1800017D8
0x1800017d3  cmp     edi, 3
0x1800017d6  jnz     short loc_180001844
0x1800017d8  mov     r8, [rsp+108h+lpvReserved]
0x1800017e0  mov     edx, edi
0x1800017e2  mov     rcx, rsi
0x1800017e5  call    _CRT_INIT
0x1800017ea  mov     ebx, eax
0x1800017ec  mov     [rsp+108h+var_E8], eax
0x1800017f0  jmp     short loc_180001807
0x1800017f2  xor     ebx, ebx
0x1800017f4  mov     [rsp+108h+var_E8], ebx
0x1800017f8  mov     edi, [rsp+108h+arg_8]
0x1800017ff  mov     rsi, [rsp+108h+arg_0]
0x180001807  mov     rax, cs:_pRawDllMain
0x18000180e  test    rax, rax
0x180001811  jz      short loc_180001844
0x180001813  cmp     cs:dword_180021564, 0
0x18000181a  jz      short loc_180001844
0x18000181c  mov     r8, [rsp+108h+lpvReserved]
0x180001824  mov     edx, edi
0x180001826  mov     rcx, rsi
0x180001829  call    cs:__guard_dispatch_icall_fptr
0x18000182f  mov     ebx, eax
0x180001831  mov     [rsp+108h+var_E8], eax
0x180001835  jmp     short loc_180001844
0x180001837  xor     ebx, ebx
0x180001839  mov     [rsp+108h+var_E8], ebx
0x18000183d  mov     edi, [rsp+108h+arg_8]
0x180001844  cmp     edi, 1
0x180001847  ja      short loc_180001853
0x180001849  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001853  mov     eax, ebx
0x180001855  add     rsp, 0F0h
0x18000185c  pop     rdi
0x18000185d  pop     rsi
0x18000185e  pop     rbx
0x18000185f  retn
0x180018610  push    rbp
0x180018612  sub     rsp, 20h
0x180018616  mov     rbp, rdx
0x180018619  mov     rax, [rcx]
0x18001861c  mov     edx, [rax]
0x18001861e  mov     [rbp+0A8h], rcx
0x180018625  mov     [rbp+28h], edx
0x180018628  mov     eax, [rbp+28h]
0x18001862b  cmp     eax, 0E06D7363h
0x180018630  jnz     short loc_180018646
0x180018632  mov     rdx, [rbp+0A8h]
0x180018639  mov     ecx, [rbp+28h]
0x18001863c  call    _XcptFilter_0
0x180018641  mov     [rbp+30h], eax
0x180018644  jmp     short loc_18001864D
0x180018646  mov     dword ptr [rbp+30h], 0
0x18001864d  mov     eax, [rbp+30h]
0x180018650  add     rsp, 20h
0x180018654  pop     rbp
0x180018655  retn
0x180018657  push    rbp
0x180018659  sub     rsp, 20h
0x18001865d  mov     rbp, rdx
0x180018660  mov     rax, [rcx]
0x180018663  mov     edx, [rax]
0x180018665  mov     [rbp+0B0h], rcx
0x18001866c  mov     [rbp+38h], edx
0x18001866f  mov     eax, [rbp+38h]
0x180018672  cmp     eax, 0E06D7363h
0x180018677  jnz     short loc_18001868D
0x180018679  mov     rdx, [rbp+0B0h]
0x180018680  mov     ecx, [rbp+38h]
0x180018683  call    _XcptFilter_0
0x180018688  mov     [rbp+40h], eax
0x18001868b  jmp     short loc_180018694
0x18001868d  mov     dword ptr [rbp+40h], 0
0x180018694  mov     eax, [rbp+40h]
0x180018697  add     rsp, 20h
0x18001869b  pop     rbp
0x18001869c  retn
0x18001869e  push    rbp
0x1800186a0  sub     rsp, 20h
0x1800186a4  mov     rbp, rdx
0x1800186a7  mov     rax, [rcx]
0x1800186aa  mov     edx, [rax]
0x1800186ac  mov     [rbp+0B8h], rcx
0x1800186b3  mov     [rbp+48h], edx
0x1800186b6  mov     eax, [rbp+48h]
0x1800186b9  cmp     eax, 0E06D7363h
0x1800186be  jnz     short loc_1800186D4
0x1800186c0  mov     rdx, [rbp+0B8h]
0x1800186c7  mov     ecx, [rbp+48h]
0x1800186ca  call    _XcptFilter_0
0x1800186cf  mov     [rbp+50h], eax
0x1800186d2  jmp     short loc_1800186DB
0x1800186d4  mov     dword ptr [rbp+50h], 0
0x1800186db  mov     eax, [rbp+50h]
0x1800186de  add     rsp, 20h
0x1800186e2  pop     rbp
0x1800186e3  retn
0x1800186e5  push    rbp
0x1800186e7  sub     rsp, 20h
0x1800186eb  mov     rbp, rdx
0x1800186ee  mov     rax, [rcx]
0x1800186f1  mov     edx, [rax]
0x1800186f3  mov     [rbp+0C0h], rcx
0x1800186fa  mov     [rbp+58h], edx
0x1800186fd  mov     eax, [rbp+58h]
0x180018700  cmp     eax, 0E06D7363h
0x180018705  jnz     short loc_18001871B
0x180018707  mov     rdx, [rbp+0C0h]
0x18001870e  mov     ecx, [rbp+58h]
0x180018711  call    _XcptFilter_0
0x180018716  mov     [rbp+60h], eax
0x180018719  jmp     short loc_180018722
0x18001871b  mov     dword ptr [rbp+60h], 0
0x180018722  mov     eax, [rbp+60h]
0x180018725  add     rsp, 20h
0x180018729  pop     rbp
0x18001872a  retn
0x18001872c  push    rbp
0x18001872e  sub     rsp, 20h
0x180018732  mov     rbp, rdx
0x180018735  mov     rax, [rcx]
0x180018738  mov     edx, [rax]
0x18001873a  mov     [rbp+0C8h], rcx
0x180018741  mov     [rbp+68h], edx
0x180018744  mov     eax, [rbp+68h]
0x180018747  cmp     eax, 0E06D7363h
0x18001874c  jnz     short loc_180018762
0x18001874e  mov     rdx, [rbp+0C8h]
0x180018755  mov     ecx, [rbp+68h]
0x180018758  call    _XcptFilter_0
0x18001875d  mov     [rbp+70h], eax
0x180018760  jmp     short loc_180018769
0x180018762  mov     dword ptr [rbp+70h], 0
0x180018769  mov     eax, [rbp+70h]
0x18001876c  add     rsp, 20h
0x180018770  pop     rbp
0x180018771  retn
0x180018773  push    rbp
0x180018775  sub     rsp, 20h
0x180018779  mov     rbp, rdx
0x18001877c  mov     rax, [rcx]
0x18001877f  mov     edx, [rax]
0x180018781  mov     [rbp+0D0h], rcx
0x180018788  mov     [rbp+78h], edx
0x18001878b  mov     eax, [rbp+78h]
0x18001878e  cmp     eax, 0E06D7363h
0x180018793  jnz     short loc_1800187AC
0x180018795  mov     rdx, [rbp+0D0h]
0x18001879c  mov     ecx, [rbp+78h]
0x18001879f  call    _XcptFilter_0
0x1800187a4  mov     [rbp+80h], eax
0x1800187aa  jmp     short loc_1800187B6
0x1800187ac  mov     dword ptr [rbp+80h], 0
0x1800187b6  mov     eax, [rbp+80h]
0x1800187bc  add     rsp, 20h
0x1800187c0  pop     rbp
0x1800187c1  retn
0x1800187c3  push    rbp
0x1800187c5  sub     rsp, 20h
0x1800187c9  mov     rbp, rdx
0x1800187cc  mov     rax, [rcx]
0x1800187cf  mov     edx, [rax]
0x1800187d1  mov     [rbp+0D8h], rcx
0x1800187d8  mov     [rbp+88h], edx
0x1800187de  mov     eax, [rbp+88h]
0x1800187e4  cmp     eax, 0E06D7363h
0x1800187e9  jnz     short loc_180018805
0x1800187eb  mov     rdx, [rbp+0D8h]
0x1800187f2  mov     ecx, [rbp+88h]
0x1800187f8  call    _XcptFilter_0
0x1800187fd  mov     [rbp+90h], eax
0x180018803  jmp     short loc_18001880F
0x180018805  mov     dword ptr [rbp+90h], 0
0x18001880f  mov     eax, [rbp+90h]
0x180018815  add     rsp, 20h
0x180018819  pop     rbp
0x18001881a  retn
0x18001881c  push    rbp
0x18001881e  sub     rsp, 20h
0x180018822  mov     rbp, rdx
0x180018825  mov     rax, [rcx]
0x180018828  mov     edx, [rax]
0x18001882a  mov     [rbp+0E0h], rcx
0x180018831  mov     [rbp+98h], edx
0x180018837  mov     eax, [rbp+98h]
0x18001883d  cmp     eax, 0E06D7363h
0x180018842  jnz     short loc_18001885E
0x180018844  mov     rdx, [rbp+0E0h]
0x18001884b  mov     ecx, [rbp+98h]
0x180018851  call    _XcptFilter_0
0x180018856  mov     [rbp+0A0h], eax
0x18001885c  jmp     short loc_180018868
0x18001885e  mov     dword ptr [rbp+0A0h], 0
0x180018868  mov     eax, [rbp+0A0h]
0x18001886e  add     rsp, 20h
0x180018872  pop     rbp
0x180018873  retn
0x180018875  push    rbp
0x180018877  sub     rsp, 20h
0x18001887b  mov     rbp, rdx
0x18001887e  cmp     dword ptr [rbp+118h], 1
0x180018885  ja      short loc_180018891
0x180018887  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
