# __DllMainCRTStartup

- ea: `0x180001834`
- end: `0x180001a40`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800017f0`

## callees

- `0x1800015c0`
- `0x180001834`
- `0x180001fce`
- `0x180012cbc`
- `0x180013720`

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
  if ( (_DWORD)fdwReason || dword_18001D3DC )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001D3E0 = 1;
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
            if ( dword_18001D3E0 )
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
0x180001834  mov     [rsp+lpvReserved], r8
0x180001839  mov     [rsp+arg_8], edx
0x18000183d  mov     [rsp+arg_0], rcx
0x180001842  push    rbx
0x180001843  push    rsi
0x180001844  push    rdi
0x180001845  sub     rsp, 0F0h
0x18000184c  mov     edi, edx
0x18000184e  mov     rsi, rcx
0x180001851  mov     ebx, 1
0x180001856  cmp     edx, ebx
0x180001858  ja      short loc_180001860
0x18000185a  mov     cs:__native_dllmain_reason, edx
0x180001860  test    edx, edx
0x180001862  jnz     short loc_180001877
0x180001864  cmp     cs:dword_18001D3DC, edx
0x18000186a  jnz     short loc_180001877
0x18000186c  xor     ebx, ebx
0x18000186e  mov     [rsp+108h+var_E8], ebx
0x180001872  jmp     loc_180001A24
0x180001877  lea     eax, [rdx-1]
0x18000187a  cmp     eax, 1
0x18000187d  ja      loc_180001904
0x180001883  mov     rax, cs:_pRawDllMain
0x18000188a  test    rax, rax
0x18000188d  jz      short loc_1800018C5
0x18000188f  cmp     edx, 1
0x180001892  jnz     short loc_18000189A
0x180001894  mov     cs:dword_18001D3E0, edx
0x18000189a  mov     r8, [rsp+108h+lpvReserved]
0x1800018a2  call    cs:__guard_dispatch_icall_fptr
0x1800018a8  mov     ebx, eax
0x1800018aa  mov     [rsp+108h+var_E8], eax
0x1800018ae  jmp     short loc_1800018C5
0x1800018b0  xor     ebx, ebx
0x1800018b2  mov     [rsp+108h+var_E8], ebx
0x1800018b6  mov     edi, [rsp+108h+arg_8]
0x1800018bd  mov     rsi, [rsp+108h+arg_0]
0x1800018c5  test    ebx, ebx
0x1800018c7  jz      loc_180001A24
0x1800018cd  mov     r8, [rsp+108h+lpvReserved]
0x1800018d5  mov     edx, edi
0x1800018d7  mov     rcx, rsi
0x1800018da  call    _CRT_INIT
0x1800018df  mov     ebx, eax
0x1800018e1  mov     [rsp+108h+var_E8], eax
0x1800018e5  jmp     short loc_1800018FC
0x1800018e7  xor     ebx, ebx
0x1800018e9  mov     [rsp+108h+var_E8], ebx
0x1800018ed  mov     edi, [rsp+108h+arg_8]
0x1800018f4  mov     rsi, [rsp+108h+arg_0]
0x1800018fc  test    ebx, ebx
0x1800018fe  jz      loc_180001A24
0x180001904  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000190c  mov     edx, edi; fdwReason
0x18000190e  mov     rcx, rsi; hinstDLL
0x180001911  call    DllMain
0x180001916  mov     ebx, eax
0x180001918  mov     [rsp+108h+var_E8], eax
0x18000191c  jmp     short loc_180001933
0x18000191e  xor     ebx, ebx
0x180001920  mov     [rsp+108h+var_E8], ebx
0x180001924  mov     edi, [rsp+108h+arg_8]
0x18000192b  mov     rsi, [rsp+108h+arg_0]
0x180001933  cmp     edi, 1
0x180001936  jnz     short loc_1800019AF
0x180001938  test    ebx, ebx
0x18000193a  jnz     short loc_1800019AF
0x18000193c  xor     r8d, r8d; lpvReserved
0x18000193f  xor     edx, edx; fdwReason
0x180001941  mov     rcx, rsi; hinstDLL
0x180001944  call    DllMain
0x180001949  jmp     short loc_18000195E
0x18000194b  mov     edi, [rsp+108h+arg_8]
0x180001952  mov     rsi, [rsp+108h+arg_0]
0x18000195a  mov     ebx, [rsp+108h+var_E8]
0x18000195e  xor     r8d, r8d
0x180001961  xor     edx, edx
0x180001963  mov     rcx, rsi
0x180001966  call    _CRT_INIT
0x18000196b  jmp     short loc_180001980
0x18000196d  mov     edi, [rsp+108h+arg_8]
0x180001974  mov     rsi, [rsp+108h+arg_0]
0x18000197c  mov     ebx, [rsp+108h+var_E8]
0x180001980  mov     rax, cs:_pRawDllMain
0x180001987  test    rax, rax
0x18000198a  jz      short loc_1800019AF
0x18000198c  xor     r8d, r8d
0x18000198f  xor     edx, edx
0x180001991  mov     rcx, rsi
0x180001994  call    cs:__guard_dispatch_icall_fptr
0x18000199a  jmp     short loc_1800019AF
0x18000199c  mov     edi, [rsp+108h+arg_8]
0x1800019a3  mov     rsi, [rsp+108h+arg_0]
0x1800019ab  mov     ebx, [rsp+108h+var_E8]
0x1800019af  test    edi, edi
0x1800019b1  jz      short loc_1800019B8
0x1800019b3  cmp     edi, 3
0x1800019b6  jnz     short loc_180001A24
0x1800019b8  mov     r8, [rsp+108h+lpvReserved]
0x1800019c0  mov     edx, edi
0x1800019c2  mov     rcx, rsi
0x1800019c5  call    _CRT_INIT
0x1800019ca  mov     ebx, eax
0x1800019cc  mov     [rsp+108h+var_E8], eax
0x1800019d0  jmp     short loc_1800019E7
0x1800019d2  xor     ebx, ebx
0x1800019d4  mov     [rsp+108h+var_E8], ebx
0x1800019d8  mov     edi, [rsp+108h+arg_8]
0x1800019df  mov     rsi, [rsp+108h+arg_0]
0x1800019e7  mov     rax, cs:_pRawDllMain
0x1800019ee  test    rax, rax
0x1800019f1  jz      short loc_180001A24
0x1800019f3  cmp     cs:dword_18001D3E0, 0
0x1800019fa  jz      short loc_180001A24
0x1800019fc  mov     r8, [rsp+108h+lpvReserved]
0x180001a04  mov     edx, edi
0x180001a06  mov     rcx, rsi
0x180001a09  call    cs:__guard_dispatch_icall_fptr
0x180001a0f  mov     ebx, eax
0x180001a11  mov     [rsp+108h+var_E8], eax
0x180001a15  jmp     short loc_180001A24
0x180001a17  xor     ebx, ebx
0x180001a19  mov     [rsp+108h+var_E8], ebx
0x180001a1d  mov     edi, [rsp+108h+arg_8]
0x180001a24  cmp     edi, 1
0x180001a27  ja      short loc_180001A33
0x180001a29  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001a33  mov     eax, ebx
0x180001a35  add     rsp, 0F0h
0x180001a3c  pop     rdi
0x180001a3d  pop     rsi
0x180001a3e  pop     rbx
0x180001a3f  retn
0x1800137c3  push    rbp
0x1800137c5  sub     rsp, 20h
0x1800137c9  mov     rbp, rdx
0x1800137cc  mov     rax, [rcx]
0x1800137cf  mov     edx, [rax]
0x1800137d1  mov     [rbp+0A8h], rcx
0x1800137d8  mov     [rbp+28h], edx
0x1800137db  mov     eax, [rbp+28h]
0x1800137de  cmp     eax, 0E06D7363h
0x1800137e3  jnz     short loc_1800137F9
0x1800137e5  mov     rdx, [rbp+0A8h]
0x1800137ec  mov     ecx, [rbp+28h]
0x1800137ef  call    _XcptFilter_0
0x1800137f4  mov     [rbp+30h], eax
0x1800137f7  jmp     short loc_180013800
0x1800137f9  mov     dword ptr [rbp+30h], 0
0x180013800  mov     eax, [rbp+30h]
0x180013803  add     rsp, 20h
0x180013807  pop     rbp
0x180013808  retn
0x18001380a  push    rbp
0x18001380c  sub     rsp, 20h
0x180013810  mov     rbp, rdx
0x180013813  mov     rax, [rcx]
0x180013816  mov     edx, [rax]
0x180013818  mov     [rbp+0B0h], rcx
0x18001381f  mov     [rbp+38h], edx
0x180013822  mov     eax, [rbp+38h]
0x180013825  cmp     eax, 0E06D7363h
0x18001382a  jnz     short loc_180013840
0x18001382c  mov     rdx, [rbp+0B0h]
0x180013833  mov     ecx, [rbp+38h]
0x180013836  call    _XcptFilter_0
0x18001383b  mov     [rbp+40h], eax
0x18001383e  jmp     short loc_180013847
0x180013840  mov     dword ptr [rbp+40h], 0
0x180013847  mov     eax, [rbp+40h]
0x18001384a  add     rsp, 20h
0x18001384e  pop     rbp
0x18001384f  retn
0x180013851  push    rbp
0x180013853  sub     rsp, 20h
0x180013857  mov     rbp, rdx
0x18001385a  mov     rax, [rcx]
0x18001385d  mov     edx, [rax]
0x18001385f  mov     [rbp+0B8h], rcx
0x180013866  mov     [rbp+48h], edx
0x180013869  mov     eax, [rbp+48h]
0x18001386c  cmp     eax, 0E06D7363h
0x180013871  jnz     short loc_180013887
0x180013873  mov     rdx, [rbp+0B8h]
0x18001387a  mov     ecx, [rbp+48h]
0x18001387d  call    _XcptFilter_0
0x180013882  mov     [rbp+50h], eax
0x180013885  jmp     short loc_18001388E
0x180013887  mov     dword ptr [rbp+50h], 0
0x18001388e  mov     eax, [rbp+50h]
0x180013891  add     rsp, 20h
0x180013895  pop     rbp
0x180013896  retn
0x180013898  push    rbp
0x18001389a  sub     rsp, 20h
0x18001389e  mov     rbp, rdx
0x1800138a1  mov     rax, [rcx]
0x1800138a4  mov     edx, [rax]
0x1800138a6  mov     [rbp+0C0h], rcx
0x1800138ad  mov     [rbp+58h], edx
0x1800138b0  mov     eax, [rbp+58h]
0x1800138b3  cmp     eax, 0E06D7363h
0x1800138b8  jnz     short loc_1800138CE
0x1800138ba  mov     rdx, [rbp+0C0h]
0x1800138c1  mov     ecx, [rbp+58h]
0x1800138c4  call    _XcptFilter_0
0x1800138c9  mov     [rbp+60h], eax
0x1800138cc  jmp     short loc_1800138D5
0x1800138ce  mov     dword ptr [rbp+60h], 0
0x1800138d5  mov     eax, [rbp+60h]
0x1800138d8  add     rsp, 20h
0x1800138dc  pop     rbp
0x1800138dd  retn
0x1800138df  push    rbp
0x1800138e1  sub     rsp, 20h
0x1800138e5  mov     rbp, rdx
0x1800138e8  mov     rax, [rcx]
0x1800138eb  mov     edx, [rax]
0x1800138ed  mov     [rbp+0C8h], rcx
0x1800138f4  mov     [rbp+68h], edx
0x1800138f7  mov     eax, [rbp+68h]
0x1800138fa  cmp     eax, 0E06D7363h
0x1800138ff  jnz     short loc_180013915
0x180013901  mov     rdx, [rbp+0C8h]
0x180013908  mov     ecx, [rbp+68h]
0x18001390b  call    _XcptFilter_0
0x180013910  mov     [rbp+70h], eax
0x180013913  jmp     short loc_18001391C
0x180013915  mov     dword ptr [rbp+70h], 0
0x18001391c  mov     eax, [rbp+70h]
0x18001391f  add     rsp, 20h
0x180013923  pop     rbp
0x180013924  retn
0x180013926  push    rbp
0x180013928  sub     rsp, 20h
0x18001392c  mov     rbp, rdx
0x18001392f  mov     rax, [rcx]
0x180013932  mov     edx, [rax]
0x180013934  mov     [rbp+0D0h], rcx
0x18001393b  mov     [rbp+78h], edx
0x18001393e  mov     eax, [rbp+78h]
0x180013941  cmp     eax, 0E06D7363h
0x180013946  jnz     short loc_18001395F
0x180013948  mov     rdx, [rbp+0D0h]
0x18001394f  mov     ecx, [rbp+78h]
0x180013952  call    _XcptFilter_0
0x180013957  mov     [rbp+80h], eax
0x18001395d  jmp     short loc_180013969
0x18001395f  mov     dword ptr [rbp+80h], 0
0x180013969  mov     eax, [rbp+80h]
0x18001396f  add     rsp, 20h
0x180013973  pop     rbp
0x180013974  retn
0x180013976  push    rbp
0x180013978  sub     rsp, 20h
0x18001397c  mov     rbp, rdx
0x18001397f  mov     rax, [rcx]
0x180013982  mov     edx, [rax]
0x180013984  mov     [rbp+0D8h], rcx
0x18001398b  mov     [rbp+88h], edx
0x180013991  mov     eax, [rbp+88h]
0x180013997  cmp     eax, 0E06D7363h
0x18001399c  jnz     short loc_1800139B8
0x18001399e  mov     rdx, [rbp+0D8h]
0x1800139a5  mov     ecx, [rbp+88h]
0x1800139ab  call    _XcptFilter_0
0x1800139b0  mov     [rbp+90h], eax
0x1800139b6  jmp     short loc_1800139C2
0x1800139b8  mov     dword ptr [rbp+90h], 0
0x1800139c2  mov     eax, [rbp+90h]
0x1800139c8  add     rsp, 20h
0x1800139cc  pop     rbp
0x1800139cd  retn
0x1800139cf  push    rbp
0x1800139d1  sub     rsp, 20h
0x1800139d5  mov     rbp, rdx
0x1800139d8  mov     rax, [rcx]
0x1800139db  mov     edx, [rax]
0x1800139dd  mov     [rbp+0E0h], rcx
0x1800139e4  mov     [rbp+98h], edx
0x1800139ea  mov     eax, [rbp+98h]
0x1800139f0  cmp     eax, 0E06D7363h
0x1800139f5  jnz     short loc_180013A11
0x1800139f7  mov     rdx, [rbp+0E0h]
0x1800139fe  mov     ecx, [rbp+98h]
0x180013a04  call    _XcptFilter_0
0x180013a09  mov     [rbp+0A0h], eax
0x180013a0f  jmp     short loc_180013A1B
0x180013a11  mov     dword ptr [rbp+0A0h], 0
0x180013a1b  mov     eax, [rbp+0A0h]
0x180013a21  add     rsp, 20h
0x180013a25  pop     rbp
0x180013a26  retn
0x180013a28  push    rbp
0x180013a2a  sub     rsp, 20h
0x180013a2e  mov     rbp, rdx
0x180013a31  cmp     dword ptr [rbp+118h], 1
0x180013a38  ja      short loc_180013A44
0x180013a3a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
