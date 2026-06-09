# __DllMainCRTStartup

- ea: `0x1800015e4`
- end: `0x1800017f0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800015a0`

## callees

- `0x180001370`
- `0x1800015e4`
- `0x180001e2e`
- `0x180002008`
- `0x180009720`

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
  if ( (_DWORD)fdwReason || dword_1800146FC )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180014700 = 1;
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
            if ( dword_180014700 )
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
0x1800015e4  mov     [rsp+lpvReserved], r8
0x1800015e9  mov     [rsp+arg_8], edx
0x1800015ed  mov     [rsp+arg_0], rcx
0x1800015f2  push    rbx
0x1800015f3  push    rsi
0x1800015f4  push    rdi
0x1800015f5  sub     rsp, 0F0h
0x1800015fc  mov     edi, edx
0x1800015fe  mov     rsi, rcx
0x180001601  mov     ebx, 1
0x180001606  cmp     edx, ebx
0x180001608  ja      short loc_180001610
0x18000160a  mov     cs:__native_dllmain_reason, edx
0x180001610  test    edx, edx
0x180001612  jnz     short loc_180001627
0x180001614  cmp     cs:dword_1800146FC, edx
0x18000161a  jnz     short loc_180001627
0x18000161c  xor     ebx, ebx
0x18000161e  mov     [rsp+108h+var_E8], ebx
0x180001622  jmp     loc_1800017D4
0x180001627  lea     eax, [rdx-1]
0x18000162a  cmp     eax, 1
0x18000162d  ja      loc_1800016B4
0x180001633  mov     rax, cs:_pRawDllMain
0x18000163a  test    rax, rax
0x18000163d  jz      short loc_180001675
0x18000163f  cmp     edx, 1
0x180001642  jnz     short loc_18000164A
0x180001644  mov     cs:dword_180014700, edx
0x18000164a  mov     r8, [rsp+108h+lpvReserved]
0x180001652  call    cs:__guard_dispatch_icall_fptr
0x180001658  mov     ebx, eax
0x18000165a  mov     [rsp+108h+var_E8], eax
0x18000165e  jmp     short loc_180001675
0x180001660  xor     ebx, ebx
0x180001662  mov     [rsp+108h+var_E8], ebx
0x180001666  mov     edi, [rsp+108h+arg_8]
0x18000166d  mov     rsi, [rsp+108h+arg_0]
0x180001675  test    ebx, ebx
0x180001677  jz      loc_1800017D4
0x18000167d  mov     r8, [rsp+108h+lpvReserved]
0x180001685  mov     edx, edi
0x180001687  mov     rcx, rsi
0x18000168a  call    _CRT_INIT
0x18000168f  mov     ebx, eax
0x180001691  mov     [rsp+108h+var_E8], eax
0x180001695  jmp     short loc_1800016AC
0x180001697  xor     ebx, ebx
0x180001699  mov     [rsp+108h+var_E8], ebx
0x18000169d  mov     edi, [rsp+108h+arg_8]
0x1800016a4  mov     rsi, [rsp+108h+arg_0]
0x1800016ac  test    ebx, ebx
0x1800016ae  jz      loc_1800017D4
0x1800016b4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800016bc  mov     edx, edi; fdwReason
0x1800016be  mov     rcx, rsi; hinstDLL
0x1800016c1  call    DllMain
0x1800016c6  mov     ebx, eax
0x1800016c8  mov     [rsp+108h+var_E8], eax
0x1800016cc  jmp     short loc_1800016E3
0x1800016ce  xor     ebx, ebx
0x1800016d0  mov     [rsp+108h+var_E8], ebx
0x1800016d4  mov     edi, [rsp+108h+arg_8]
0x1800016db  mov     rsi, [rsp+108h+arg_0]
0x1800016e3  cmp     edi, 1
0x1800016e6  jnz     short loc_18000175F
0x1800016e8  test    ebx, ebx
0x1800016ea  jnz     short loc_18000175F
0x1800016ec  xor     r8d, r8d; lpvReserved
0x1800016ef  xor     edx, edx; fdwReason
0x1800016f1  mov     rcx, rsi; hinstDLL
0x1800016f4  call    DllMain
0x1800016f9  jmp     short loc_18000170E
0x1800016fb  mov     edi, [rsp+108h+arg_8]
0x180001702  mov     rsi, [rsp+108h+arg_0]
0x18000170a  mov     ebx, [rsp+108h+var_E8]
0x18000170e  xor     r8d, r8d
0x180001711  xor     edx, edx
0x180001713  mov     rcx, rsi
0x180001716  call    _CRT_INIT
0x18000171b  jmp     short loc_180001730
0x18000171d  mov     edi, [rsp+108h+arg_8]
0x180001724  mov     rsi, [rsp+108h+arg_0]
0x18000172c  mov     ebx, [rsp+108h+var_E8]
0x180001730  mov     rax, cs:_pRawDllMain
0x180001737  test    rax, rax
0x18000173a  jz      short loc_18000175F
0x18000173c  xor     r8d, r8d
0x18000173f  xor     edx, edx
0x180001741  mov     rcx, rsi
0x180001744  call    cs:__guard_dispatch_icall_fptr
0x18000174a  jmp     short loc_18000175F
0x18000174c  mov     edi, [rsp+108h+arg_8]
0x180001753  mov     rsi, [rsp+108h+arg_0]
0x18000175b  mov     ebx, [rsp+108h+var_E8]
0x18000175f  test    edi, edi
0x180001761  jz      short loc_180001768
0x180001763  cmp     edi, 3
0x180001766  jnz     short loc_1800017D4
0x180001768  mov     r8, [rsp+108h+lpvReserved]
0x180001770  mov     edx, edi
0x180001772  mov     rcx, rsi
0x180001775  call    _CRT_INIT
0x18000177a  mov     ebx, eax
0x18000177c  mov     [rsp+108h+var_E8], eax
0x180001780  jmp     short loc_180001797
0x180001782  xor     ebx, ebx
0x180001784  mov     [rsp+108h+var_E8], ebx
0x180001788  mov     edi, [rsp+108h+arg_8]
0x18000178f  mov     rsi, [rsp+108h+arg_0]
0x180001797  mov     rax, cs:_pRawDllMain
0x18000179e  test    rax, rax
0x1800017a1  jz      short loc_1800017D4
0x1800017a3  cmp     cs:dword_180014700, 0
0x1800017aa  jz      short loc_1800017D4
0x1800017ac  mov     r8, [rsp+108h+lpvReserved]
0x1800017b4  mov     edx, edi
0x1800017b6  mov     rcx, rsi
0x1800017b9  call    cs:__guard_dispatch_icall_fptr
0x1800017bf  mov     ebx, eax
0x1800017c1  mov     [rsp+108h+var_E8], eax
0x1800017c5  jmp     short loc_1800017D4
0x1800017c7  xor     ebx, ebx
0x1800017c9  mov     [rsp+108h+var_E8], ebx
0x1800017cd  mov     edi, [rsp+108h+arg_8]
0x1800017d4  cmp     edi, 1
0x1800017d7  ja      short loc_1800017E3
0x1800017d9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800017e3  mov     eax, ebx
0x1800017e5  add     rsp, 0F0h
0x1800017ec  pop     rdi
0x1800017ed  pop     rsi
0x1800017ee  pop     rbx
0x1800017ef  retn
0x180009760  push    rbp
0x180009762  sub     rsp, 20h
0x180009766  mov     rbp, rdx
0x180009769  mov     rax, [rcx]
0x18000976c  mov     edx, [rax]
0x18000976e  mov     [rbp+0A8h], rcx
0x180009775  mov     [rbp+28h], edx
0x180009778  mov     eax, [rbp+28h]
0x18000977b  cmp     eax, 0E06D7363h
0x180009780  jnz     short loc_180009796
0x180009782  mov     rdx, [rbp+0A8h]
0x180009789  mov     ecx, [rbp+28h]
0x18000978c  call    _XcptFilter_0
0x180009791  mov     [rbp+30h], eax
0x180009794  jmp     short loc_18000979D
0x180009796  mov     dword ptr [rbp+30h], 0
0x18000979d  mov     eax, [rbp+30h]
0x1800097a0  add     rsp, 20h
0x1800097a4  pop     rbp
0x1800097a5  retn
0x1800097a7  push    rbp
0x1800097a9  sub     rsp, 20h
0x1800097ad  mov     rbp, rdx
0x1800097b0  mov     rax, [rcx]
0x1800097b3  mov     edx, [rax]
0x1800097b5  mov     [rbp+0B0h], rcx
0x1800097bc  mov     [rbp+38h], edx
0x1800097bf  mov     eax, [rbp+38h]
0x1800097c2  cmp     eax, 0E06D7363h
0x1800097c7  jnz     short loc_1800097DD
0x1800097c9  mov     rdx, [rbp+0B0h]
0x1800097d0  mov     ecx, [rbp+38h]
0x1800097d3  call    _XcptFilter_0
0x1800097d8  mov     [rbp+40h], eax
0x1800097db  jmp     short loc_1800097E4
0x1800097dd  mov     dword ptr [rbp+40h], 0
0x1800097e4  mov     eax, [rbp+40h]
0x1800097e7  add     rsp, 20h
0x1800097eb  pop     rbp
0x1800097ec  retn
0x1800097ee  push    rbp
0x1800097f0  sub     rsp, 20h
0x1800097f4  mov     rbp, rdx
0x1800097f7  mov     rax, [rcx]
0x1800097fa  mov     edx, [rax]
0x1800097fc  mov     [rbp+0B8h], rcx
0x180009803  mov     [rbp+48h], edx
0x180009806  mov     eax, [rbp+48h]
0x180009809  cmp     eax, 0E06D7363h
0x18000980e  jnz     short loc_180009824
0x180009810  mov     rdx, [rbp+0B8h]
0x180009817  mov     ecx, [rbp+48h]
0x18000981a  call    _XcptFilter_0
0x18000981f  mov     [rbp+50h], eax
0x180009822  jmp     short loc_18000982B
0x180009824  mov     dword ptr [rbp+50h], 0
0x18000982b  mov     eax, [rbp+50h]
0x18000982e  add     rsp, 20h
0x180009832  pop     rbp
0x180009833  retn
0x180009835  push    rbp
0x180009837  sub     rsp, 20h
0x18000983b  mov     rbp, rdx
0x18000983e  mov     rax, [rcx]
0x180009841  mov     edx, [rax]
0x180009843  mov     [rbp+0C0h], rcx
0x18000984a  mov     [rbp+58h], edx
0x18000984d  mov     eax, [rbp+58h]
0x180009850  cmp     eax, 0E06D7363h
0x180009855  jnz     short loc_18000986B
0x180009857  mov     rdx, [rbp+0C0h]
0x18000985e  mov     ecx, [rbp+58h]
0x180009861  call    _XcptFilter_0
0x180009866  mov     [rbp+60h], eax
0x180009869  jmp     short loc_180009872
0x18000986b  mov     dword ptr [rbp+60h], 0
0x180009872  mov     eax, [rbp+60h]
0x180009875  add     rsp, 20h
0x180009879  pop     rbp
0x18000987a  retn
0x18000987c  push    rbp
0x18000987e  sub     rsp, 20h
0x180009882  mov     rbp, rdx
0x180009885  mov     rax, [rcx]
0x180009888  mov     edx, [rax]
0x18000988a  mov     [rbp+0C8h], rcx
0x180009891  mov     [rbp+68h], edx
0x180009894  mov     eax, [rbp+68h]
0x180009897  cmp     eax, 0E06D7363h
0x18000989c  jnz     short loc_1800098B2
0x18000989e  mov     rdx, [rbp+0C8h]
0x1800098a5  mov     ecx, [rbp+68h]
0x1800098a8  call    _XcptFilter_0
0x1800098ad  mov     [rbp+70h], eax
0x1800098b0  jmp     short loc_1800098B9
0x1800098b2  mov     dword ptr [rbp+70h], 0
0x1800098b9  mov     eax, [rbp+70h]
0x1800098bc  add     rsp, 20h
0x1800098c0  pop     rbp
0x1800098c1  retn
0x1800098c3  push    rbp
0x1800098c5  sub     rsp, 20h
0x1800098c9  mov     rbp, rdx
0x1800098cc  mov     rax, [rcx]
0x1800098cf  mov     edx, [rax]
0x1800098d1  mov     [rbp+0D0h], rcx
0x1800098d8  mov     [rbp+78h], edx
0x1800098db  mov     eax, [rbp+78h]
0x1800098de  cmp     eax, 0E06D7363h
0x1800098e3  jnz     short loc_1800098FC
0x1800098e5  mov     rdx, [rbp+0D0h]
0x1800098ec  mov     ecx, [rbp+78h]
0x1800098ef  call    _XcptFilter_0
0x1800098f4  mov     [rbp+80h], eax
0x1800098fa  jmp     short loc_180009906
0x1800098fc  mov     dword ptr [rbp+80h], 0
0x180009906  mov     eax, [rbp+80h]
0x18000990c  add     rsp, 20h
0x180009910  pop     rbp
0x180009911  retn
0x180009913  push    rbp
0x180009915  sub     rsp, 20h
0x180009919  mov     rbp, rdx
0x18000991c  mov     rax, [rcx]
0x18000991f  mov     edx, [rax]
0x180009921  mov     [rbp+0D8h], rcx
0x180009928  mov     [rbp+88h], edx
0x18000992e  mov     eax, [rbp+88h]
0x180009934  cmp     eax, 0E06D7363h
0x180009939  jnz     short loc_180009955
0x18000993b  mov     rdx, [rbp+0D8h]
0x180009942  mov     ecx, [rbp+88h]
0x180009948  call    _XcptFilter_0
0x18000994d  mov     [rbp+90h], eax
0x180009953  jmp     short loc_18000995F
0x180009955  mov     dword ptr [rbp+90h], 0
0x18000995f  mov     eax, [rbp+90h]
0x180009965  add     rsp, 20h
0x180009969  pop     rbp
0x18000996a  retn
0x18000996c  push    rbp
0x18000996e  sub     rsp, 20h
0x180009972  mov     rbp, rdx
0x180009975  mov     rax, [rcx]
0x180009978  mov     edx, [rax]
0x18000997a  mov     [rbp+0E0h], rcx
0x180009981  mov     [rbp+98h], edx
0x180009987  mov     eax, [rbp+98h]
0x18000998d  cmp     eax, 0E06D7363h
0x180009992  jnz     short loc_1800099AE
0x180009994  mov     rdx, [rbp+0E0h]
0x18000999b  mov     ecx, [rbp+98h]
0x1800099a1  call    _XcptFilter_0
0x1800099a6  mov     [rbp+0A0h], eax
0x1800099ac  jmp     short loc_1800099B8
0x1800099ae  mov     dword ptr [rbp+0A0h], 0
0x1800099b8  mov     eax, [rbp+0A0h]
0x1800099be  add     rsp, 20h
0x1800099c2  pop     rbp
0x1800099c3  retn
0x1800099c5  push    rbp
0x1800099c7  sub     rsp, 20h
0x1800099cb  mov     rbp, rdx
0x1800099ce  cmp     dword ptr [rbp+118h], 1
0x1800099d5  ja      short loc_1800099E1
0x1800099d7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
