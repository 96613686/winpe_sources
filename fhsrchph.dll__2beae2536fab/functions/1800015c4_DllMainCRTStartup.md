# __DllMainCRTStartup

- ea: `0x1800015c4`
- end: `0x1800017d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001580`

## callees

- `0x180001350`
- `0x1800015c4`
- `0x180001d1c`
- `0x180002af4`
- `0x18000abd0`

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
  if ( (_DWORD)fdwReason || dword_180011320 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180011324 = 1;
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
            if ( dword_180011324 )
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
0x1800015c4  mov     [rsp+lpvReserved], r8
0x1800015c9  mov     [rsp+arg_8], edx
0x1800015cd  mov     [rsp+arg_0], rcx
0x1800015d2  push    rbx
0x1800015d3  push    rsi
0x1800015d4  push    rdi
0x1800015d5  sub     rsp, 0F0h
0x1800015dc  mov     edi, edx
0x1800015de  mov     rsi, rcx
0x1800015e1  mov     ebx, 1
0x1800015e6  cmp     edx, ebx
0x1800015e8  ja      short loc_1800015F0
0x1800015ea  mov     cs:__native_dllmain_reason, edx
0x1800015f0  test    edx, edx
0x1800015f2  jnz     short loc_180001607
0x1800015f4  cmp     cs:dword_180011320, edx
0x1800015fa  jnz     short loc_180001607
0x1800015fc  xor     ebx, ebx
0x1800015fe  mov     [rsp+108h+var_E8], ebx
0x180001602  jmp     loc_1800017B4
0x180001607  lea     eax, [rdx-1]
0x18000160a  cmp     eax, 1
0x18000160d  ja      loc_180001694
0x180001613  mov     rax, cs:_pRawDllMain
0x18000161a  test    rax, rax
0x18000161d  jz      short loc_180001655
0x18000161f  cmp     edx, 1
0x180001622  jnz     short loc_18000162A
0x180001624  mov     cs:dword_180011324, edx
0x18000162a  mov     r8, [rsp+108h+lpvReserved]
0x180001632  call    cs:__guard_dispatch_icall_fptr
0x180001638  mov     ebx, eax
0x18000163a  mov     [rsp+108h+var_E8], eax
0x18000163e  jmp     short loc_180001655
0x180001640  xor     ebx, ebx
0x180001642  mov     [rsp+108h+var_E8], ebx
0x180001646  mov     edi, [rsp+108h+arg_8]
0x18000164d  mov     rsi, [rsp+108h+arg_0]
0x180001655  test    ebx, ebx
0x180001657  jz      loc_1800017B4
0x18000165d  mov     r8, [rsp+108h+lpvReserved]
0x180001665  mov     edx, edi
0x180001667  mov     rcx, rsi
0x18000166a  call    _CRT_INIT
0x18000166f  mov     ebx, eax
0x180001671  mov     [rsp+108h+var_E8], eax
0x180001675  jmp     short loc_18000168C
0x180001677  xor     ebx, ebx
0x180001679  mov     [rsp+108h+var_E8], ebx
0x18000167d  mov     edi, [rsp+108h+arg_8]
0x180001684  mov     rsi, [rsp+108h+arg_0]
0x18000168c  test    ebx, ebx
0x18000168e  jz      loc_1800017B4
0x180001694  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000169c  mov     edx, edi; fdwReason
0x18000169e  mov     rcx, rsi; hinstDLL
0x1800016a1  call    DllMain
0x1800016a6  mov     ebx, eax
0x1800016a8  mov     [rsp+108h+var_E8], eax
0x1800016ac  jmp     short loc_1800016C3
0x1800016ae  xor     ebx, ebx
0x1800016b0  mov     [rsp+108h+var_E8], ebx
0x1800016b4  mov     edi, [rsp+108h+arg_8]
0x1800016bb  mov     rsi, [rsp+108h+arg_0]
0x1800016c3  cmp     edi, 1
0x1800016c6  jnz     short loc_18000173F
0x1800016c8  test    ebx, ebx
0x1800016ca  jnz     short loc_18000173F
0x1800016cc  xor     r8d, r8d; lpvReserved
0x1800016cf  xor     edx, edx; fdwReason
0x1800016d1  mov     rcx, rsi; hinstDLL
0x1800016d4  call    DllMain
0x1800016d9  jmp     short loc_1800016EE
0x1800016db  mov     edi, [rsp+108h+arg_8]
0x1800016e2  mov     rsi, [rsp+108h+arg_0]
0x1800016ea  mov     ebx, [rsp+108h+var_E8]
0x1800016ee  xor     r8d, r8d
0x1800016f1  xor     edx, edx
0x1800016f3  mov     rcx, rsi
0x1800016f6  call    _CRT_INIT
0x1800016fb  jmp     short loc_180001710
0x1800016fd  mov     edi, [rsp+108h+arg_8]
0x180001704  mov     rsi, [rsp+108h+arg_0]
0x18000170c  mov     ebx, [rsp+108h+var_E8]
0x180001710  mov     rax, cs:_pRawDllMain
0x180001717  test    rax, rax
0x18000171a  jz      short loc_18000173F
0x18000171c  xor     r8d, r8d
0x18000171f  xor     edx, edx
0x180001721  mov     rcx, rsi
0x180001724  call    cs:__guard_dispatch_icall_fptr
0x18000172a  jmp     short loc_18000173F
0x18000172c  mov     edi, [rsp+108h+arg_8]
0x180001733  mov     rsi, [rsp+108h+arg_0]
0x18000173b  mov     ebx, [rsp+108h+var_E8]
0x18000173f  test    edi, edi
0x180001741  jz      short loc_180001748
0x180001743  cmp     edi, 3
0x180001746  jnz     short loc_1800017B4
0x180001748  mov     r8, [rsp+108h+lpvReserved]
0x180001750  mov     edx, edi
0x180001752  mov     rcx, rsi
0x180001755  call    _CRT_INIT
0x18000175a  mov     ebx, eax
0x18000175c  mov     [rsp+108h+var_E8], eax
0x180001760  jmp     short loc_180001777
0x180001762  xor     ebx, ebx
0x180001764  mov     [rsp+108h+var_E8], ebx
0x180001768  mov     edi, [rsp+108h+arg_8]
0x18000176f  mov     rsi, [rsp+108h+arg_0]
0x180001777  mov     rax, cs:_pRawDllMain
0x18000177e  test    rax, rax
0x180001781  jz      short loc_1800017B4
0x180001783  cmp     cs:dword_180011324, 0
0x18000178a  jz      short loc_1800017B4
0x18000178c  mov     r8, [rsp+108h+lpvReserved]
0x180001794  mov     edx, edi
0x180001796  mov     rcx, rsi
0x180001799  call    cs:__guard_dispatch_icall_fptr
0x18000179f  mov     ebx, eax
0x1800017a1  mov     [rsp+108h+var_E8], eax
0x1800017a5  jmp     short loc_1800017B4
0x1800017a7  xor     ebx, ebx
0x1800017a9  mov     [rsp+108h+var_E8], ebx
0x1800017ad  mov     edi, [rsp+108h+arg_8]
0x1800017b4  cmp     edi, 1
0x1800017b7  ja      short loc_1800017C3
0x1800017b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800017c3  mov     eax, ebx
0x1800017c5  add     rsp, 0F0h
0x1800017cc  pop     rdi
0x1800017cd  pop     rsi
0x1800017ce  pop     rbx
0x1800017cf  retn
0x18000ac73  push    rbp
0x18000ac75  sub     rsp, 20h
0x18000ac79  mov     rbp, rdx
0x18000ac7c  mov     rax, [rcx]
0x18000ac7f  mov     edx, [rax]
0x18000ac81  mov     [rbp+0A8h], rcx
0x18000ac88  mov     [rbp+28h], edx
0x18000ac8b  mov     eax, [rbp+28h]
0x18000ac8e  cmp     eax, 0E06D7363h
0x18000ac93  jnz     short loc_18000ACA9
0x18000ac95  mov     rdx, [rbp+0A8h]
0x18000ac9c  mov     ecx, [rbp+28h]
0x18000ac9f  call    _XcptFilter_0
0x18000aca4  mov     [rbp+30h], eax
0x18000aca7  jmp     short loc_18000ACB0
0x18000aca9  mov     dword ptr [rbp+30h], 0
0x18000acb0  mov     eax, [rbp+30h]
0x18000acb3  add     rsp, 20h
0x18000acb7  pop     rbp
0x18000acb8  retn
0x18000acba  push    rbp
0x18000acbc  sub     rsp, 20h
0x18000acc0  mov     rbp, rdx
0x18000acc3  mov     rax, [rcx]
0x18000acc6  mov     edx, [rax]
0x18000acc8  mov     [rbp+0B0h], rcx
0x18000accf  mov     [rbp+38h], edx
0x18000acd2  mov     eax, [rbp+38h]
0x18000acd5  cmp     eax, 0E06D7363h
0x18000acda  jnz     short loc_18000ACF0
0x18000acdc  mov     rdx, [rbp+0B0h]
0x18000ace3  mov     ecx, [rbp+38h]
0x18000ace6  call    _XcptFilter_0
0x18000aceb  mov     [rbp+40h], eax
0x18000acee  jmp     short loc_18000ACF7
0x18000acf0  mov     dword ptr [rbp+40h], 0
0x18000acf7  mov     eax, [rbp+40h]
0x18000acfa  add     rsp, 20h
0x18000acfe  pop     rbp
0x18000acff  retn
0x18000ad01  push    rbp
0x18000ad03  sub     rsp, 20h
0x18000ad07  mov     rbp, rdx
0x18000ad0a  mov     rax, [rcx]
0x18000ad0d  mov     edx, [rax]
0x18000ad0f  mov     [rbp+0B8h], rcx
0x18000ad16  mov     [rbp+48h], edx
0x18000ad19  mov     eax, [rbp+48h]
0x18000ad1c  cmp     eax, 0E06D7363h
0x18000ad21  jnz     short loc_18000AD37
0x18000ad23  mov     rdx, [rbp+0B8h]
0x18000ad2a  mov     ecx, [rbp+48h]
0x18000ad2d  call    _XcptFilter_0
0x18000ad32  mov     [rbp+50h], eax
0x18000ad35  jmp     short loc_18000AD3E
0x18000ad37  mov     dword ptr [rbp+50h], 0
0x18000ad3e  mov     eax, [rbp+50h]
0x18000ad41  add     rsp, 20h
0x18000ad45  pop     rbp
0x18000ad46  retn
0x18000ad48  push    rbp
0x18000ad4a  sub     rsp, 20h
0x18000ad4e  mov     rbp, rdx
0x18000ad51  mov     rax, [rcx]
0x18000ad54  mov     edx, [rax]
0x18000ad56  mov     [rbp+0C0h], rcx
0x18000ad5d  mov     [rbp+58h], edx
0x18000ad60  mov     eax, [rbp+58h]
0x18000ad63  cmp     eax, 0E06D7363h
0x18000ad68  jnz     short loc_18000AD7E
0x18000ad6a  mov     rdx, [rbp+0C0h]
0x18000ad71  mov     ecx, [rbp+58h]
0x18000ad74  call    _XcptFilter_0
0x18000ad79  mov     [rbp+60h], eax
0x18000ad7c  jmp     short loc_18000AD85
0x18000ad7e  mov     dword ptr [rbp+60h], 0
0x18000ad85  mov     eax, [rbp+60h]
0x18000ad88  add     rsp, 20h
0x18000ad8c  pop     rbp
0x18000ad8d  retn
0x18000ad8f  push    rbp
0x18000ad91  sub     rsp, 20h
0x18000ad95  mov     rbp, rdx
0x18000ad98  mov     rax, [rcx]
0x18000ad9b  mov     edx, [rax]
0x18000ad9d  mov     [rbp+0C8h], rcx
0x18000ada4  mov     [rbp+68h], edx
0x18000ada7  mov     eax, [rbp+68h]
0x18000adaa  cmp     eax, 0E06D7363h
0x18000adaf  jnz     short loc_18000ADC5
0x18000adb1  mov     rdx, [rbp+0C8h]
0x18000adb8  mov     ecx, [rbp+68h]
0x18000adbb  call    _XcptFilter_0
0x18000adc0  mov     [rbp+70h], eax
0x18000adc3  jmp     short loc_18000ADCC
0x18000adc5  mov     dword ptr [rbp+70h], 0
0x18000adcc  mov     eax, [rbp+70h]
0x18000adcf  add     rsp, 20h
0x18000add3  pop     rbp
0x18000add4  retn
0x18000add6  push    rbp
0x18000add8  sub     rsp, 20h
0x18000addc  mov     rbp, rdx
0x18000addf  mov     rax, [rcx]
0x18000ade2  mov     edx, [rax]
0x18000ade4  mov     [rbp+0D0h], rcx
0x18000adeb  mov     [rbp+78h], edx
0x18000adee  mov     eax, [rbp+78h]
0x18000adf1  cmp     eax, 0E06D7363h
0x18000adf6  jnz     short loc_18000AE0F
0x18000adf8  mov     rdx, [rbp+0D0h]
0x18000adff  mov     ecx, [rbp+78h]
0x18000ae02  call    _XcptFilter_0
0x18000ae07  mov     [rbp+80h], eax
0x18000ae0d  jmp     short loc_18000AE19
0x18000ae0f  mov     dword ptr [rbp+80h], 0
0x18000ae19  mov     eax, [rbp+80h]
0x18000ae1f  add     rsp, 20h
0x18000ae23  pop     rbp
0x18000ae24  retn
0x18000ae26  push    rbp
0x18000ae28  sub     rsp, 20h
0x18000ae2c  mov     rbp, rdx
0x18000ae2f  mov     rax, [rcx]
0x18000ae32  mov     edx, [rax]
0x18000ae34  mov     [rbp+0D8h], rcx
0x18000ae3b  mov     [rbp+88h], edx
0x18000ae41  mov     eax, [rbp+88h]
0x18000ae47  cmp     eax, 0E06D7363h
0x18000ae4c  jnz     short loc_18000AE68
0x18000ae4e  mov     rdx, [rbp+0D8h]
0x18000ae55  mov     ecx, [rbp+88h]
0x18000ae5b  call    _XcptFilter_0
0x18000ae60  mov     [rbp+90h], eax
0x18000ae66  jmp     short loc_18000AE72
0x18000ae68  mov     dword ptr [rbp+90h], 0
0x18000ae72  mov     eax, [rbp+90h]
0x18000ae78  add     rsp, 20h
0x18000ae7c  pop     rbp
0x18000ae7d  retn
0x18000ae7f  push    rbp
0x18000ae81  sub     rsp, 20h
0x18000ae85  mov     rbp, rdx
0x18000ae88  mov     rax, [rcx]
0x18000ae8b  mov     edx, [rax]
0x18000ae8d  mov     [rbp+0E0h], rcx
0x18000ae94  mov     [rbp+98h], edx
0x18000ae9a  mov     eax, [rbp+98h]
0x18000aea0  cmp     eax, 0E06D7363h
0x18000aea5  jnz     short loc_18000AEC1
0x18000aea7  mov     rdx, [rbp+0E0h]
0x18000aeae  mov     ecx, [rbp+98h]
0x18000aeb4  call    _XcptFilter_0
0x18000aeb9  mov     [rbp+0A0h], eax
0x18000aebf  jmp     short loc_18000AECB
0x18000aec1  mov     dword ptr [rbp+0A0h], 0
0x18000aecb  mov     eax, [rbp+0A0h]
0x18000aed1  add     rsp, 20h
0x18000aed5  pop     rbp
0x18000aed6  retn
0x18000aed8  push    rbp
0x18000aeda  sub     rsp, 20h
0x18000aede  mov     rbp, rdx
0x18000aee1  cmp     dword ptr [rbp+118h], 1
0x18000aee8  ja      short loc_18000AEF4
0x18000aeea  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
