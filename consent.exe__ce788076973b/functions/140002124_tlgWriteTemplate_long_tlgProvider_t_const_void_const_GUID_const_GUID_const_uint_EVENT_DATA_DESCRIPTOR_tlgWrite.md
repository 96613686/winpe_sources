# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)

- ea: `0x140002124`
- end: `0x140002540`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z`
- size: `1052`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001d8c0`

## callees

- `0x140009bc0`
- `0x14001e050`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(&dword_140029078, a2, 0);
}

```

## disassembly

```asm
0x140002124  mov     [rsp-8+arg_0], rbx
0x140002129  push    rbp
0x14000212a  lea     rbp, [rsp-1F0h]
0x140002132  sub     rsp, 2F0h
0x140002139  mov     rax, cs:__security_cookie
0x140002140  xor     rax, rsp
0x140002143  mov     [rbp+1F0h+var_10], rax
0x14000214a  mov     rax, [rbp+1F0h+arg_118]
0x140002151  xor     ebx, ebx
0x140002153  mov     [rbp+1F0h+var_20], rax
0x14000215a  mov     rax, [rbp+1F0h+arg_110]
0x140002161  mov     [rbp+1F0h+var_30], rax
0x140002168  mov     rax, [rbp+1F0h+arg_108]
0x14000216f  mov     [rbp+1F0h+var_18], 1
0x14000217a  mov     [rbp+1F0h+var_28], 4
0x140002185  mov     [rbp+1F0h+var_48], 2
0x140002190  lea     rcx, [rax+8]
0x140002194  mov     [rbp+1F0h+var_34], ebx
0x14000219a  mov     rax, [rax]
0x14000219d  mov     [rbp+1F0h+var_40], rax
0x1400021a4  movzx   eax, word ptr [rcx]
0x1400021a7  mov     [rbp+1F0h+var_38], eax
0x1400021ad  mov     rax, [rbp+1F0h+arg_100]
0x1400021b4  mov     [rbp+1F0h+var_60], rax
0x1400021bb  mov     rax, [rbp+1F0h+arg_F8]
0x1400021c2  mov     [rbp+1F0h+var_70], rax
0x1400021c9  mov     rax, [rbp+1F0h+arg_F0]
0x1400021d0  mov     [rbp+1F0h+var_50], rcx
0x1400021d7  mov     [rbp+1F0h+var_58], 1
0x1400021e2  mov     [rbp+1F0h+var_68], 8
0x1400021ed  lea     rcx, [rax+8]
0x1400021f1  mov     [rbp+1F0h+var_88], 2
0x1400021fc  mov     rax, [rax]
0x1400021ff  mov     [rbp+1F0h+var_80], rax
0x140002206  movzx   eax, word ptr [rcx]
0x140002209  mov     [rbp+1F0h+var_78], eax
0x14000220f  mov     rax, [rbp+1F0h+arg_E8]
0x140002216  mov     [rbp+1F0h+var_A0], rax
0x14000221d  mov     rax, [rbp+1F0h+arg_E0]
0x140002224  mov     [rbp+1F0h+var_B0], rax
0x14000222b  mov     rax, [rbp+1F0h+arg_D8]
0x140002232  mov     [rbp+1F0h+var_90], rcx
0x140002239  mov     [rbp+1F0h+var_74], ebx
0x14000223f  mov     [rbp+1F0h+var_98], 1
0x14000224a  lea     rcx, [rax+8]
0x14000224e  mov     [rbp+1F0h+var_A8], 8
0x140002259  mov     rax, [rax]
0x14000225c  mov     [rbp+1F0h+var_C0], rax
0x140002263  movzx   eax, word ptr [rcx]
0x140002266  mov     [rbp+1F0h+var_B8], eax
0x14000226c  mov     rax, [rbp+1F0h+arg_D0]
0x140002273  mov     [rbp+1F0h+var_E0], rax
0x14000227a  mov     rax, [rbp+1F0h+arg_C8]
0x140002281  mov     [rbp+1F0h+var_F0], rax
0x140002288  mov     rax, [rbp+1F0h+arg_C0]
0x14000228f  mov     [rbp+1F0h+var_D0], rcx
0x140002296  mov     [rbp+1F0h+var_C8], 2
0x1400022a1  mov     [rbp+1F0h+var_B4], ebx
0x1400022a7  lea     rcx, [rax+8]
0x1400022ab  mov     [rbp+1F0h+var_D8], 1
0x1400022b6  mov     rax, [rax]
0x1400022b9  mov     [rbp+1F0h+var_100], rax
0x1400022c0  movzx   eax, word ptr [rcx]
0x1400022c3  mov     [rbp+1F0h+var_F8], eax
0x1400022c9  mov     rax, [rbp+1F0h+arg_B8]
0x1400022d0  mov     [rbp+1F0h+var_120], rax
0x1400022d7  mov     rax, [rbp+1F0h+arg_B0]
0x1400022de  mov     [rbp+1F0h+var_130], rax
0x1400022e5  mov     rax, [rbp+1F0h+arg_A8]
0x1400022ec  mov     [rbp+1F0h+var_110], rcx
0x1400022f3  mov     [rbp+1F0h+var_E8], 8
0x1400022fe  mov     [rbp+1F0h+var_108], 2
0x140002309  lea     rcx, [rax+8]
0x14000230d  mov     [rbp+1F0h+var_F4], ebx
0x140002313  mov     rax, [rax]
0x140002316  mov     [rbp+1F0h+var_140], rax
0x14000231d  movzx   eax, word ptr [rcx]
0x140002320  mov     [rbp+1F0h+var_138], eax
0x140002326  mov     rax, [rbp+1F0h+arg_A0]
0x14000232d  mov     [rbp+1F0h+var_160], rax
0x140002334  mov     rax, [rbp+1F0h+arg_98]
0x14000233b  mov     [rbp+1F0h+var_170], rax
0x140002342  mov     [rbp+1F0h+var_118], 1
0x14000234d  mov     [rbp+1F0h+var_128], 8
0x140002358  mov     [rbp+1F0h+var_150], rcx
0x14000235f  mov     [rbp+1F0h+var_148], 2
0x14000236a  mov     [rbp+1F0h+var_134], ebx
0x140002370  mov     [rbp+1F0h+var_158], 1
0x14000237b  mov     rax, [rbp+1F0h+arg_90]
0x140002382  xor     r9d, r9d
0x140002385  xor     r8d, r8d
0x140002388  mov     [rbp+1F0h+var_168], 8
0x140002393  mov     [rbp+1F0h+var_188], 2
0x14000239b  mov     [rbp+1F0h+var_174], ebx
0x14000239e  lea     rcx, [rax+8]
0x1400023a2  mov     [rbp+1F0h+var_198], 1
0x1400023aa  mov     rax, [rax]
0x1400023ad  mov     [rbp+1F0h+var_180], rax
0x1400023b1  movzx   eax, word ptr [rcx]
0x1400023b4  mov     [rbp+1F0h+var_178], eax
0x1400023b7  mov     rax, [rbp+1F0h+arg_88]
0x1400023be  mov     [rbp+1F0h+var_1A0], rax
0x1400023c2  mov     rax, [rbp+1F0h+arg_80]
0x1400023c9  mov     [rbp+1F0h+var_1B0], rax
0x1400023cd  mov     rax, [rbp+1F0h+arg_78]
0x1400023d4  mov     [rbp+1F0h+var_190], rcx
0x1400023d8  mov     [rbp+1F0h+var_1A8], 8
0x1400023e0  mov     [rbp+1F0h+var_1C8], 2
0x1400023e8  lea     rcx, [rax+8]
0x1400023ec  mov     [rbp+1F0h+var_1B4], ebx
0x1400023ef  mov     rax, [rax]
0x1400023f2  mov     [rbp+1F0h+var_1C0], rax
0x1400023f6  movzx   eax, word ptr [rcx]
0x1400023f9  mov     [rbp+1F0h+var_1B8], eax
0x1400023fc  mov     rax, [rbp+1F0h+arg_70]
0x140002403  mov     [rbp+1F0h+var_1E0], rax
0x140002407  mov     rax, [rbp+1F0h+arg_68]
0x14000240e  mov     [rbp+1F0h+var_1F0], rax
0x140002412  mov     rax, [rbp+1F0h+arg_60]
0x140002419  mov     [rbp+1F0h+var_1D0], rcx
0x14000241d  mov     [rbp+1F0h+var_1D8], 1
0x140002425  mov     [rbp+1F0h+var_1E8], 8
0x14000242d  lea     rcx, [rax+8]
0x140002431  mov     [rbp+1F0h+var_208], 2
0x140002439  mov     rax, [rax]
0x14000243c  mov     [rbp+1F0h+var_200], rax
0x140002440  movzx   eax, word ptr [rcx]
0x140002443  mov     [rbp+1F0h+var_1F8], eax
0x140002446  mov     rax, [rbp+1F0h+arg_58]
0x14000244d  mov     [rbp+1F0h+var_220], rax
0x140002451  mov     rax, [rbp+1F0h+arg_50]
0x140002458  mov     [rbp+1F0h+var_230], rax
0x14000245c  mov     rax, [rbp+1F0h+arg_48]
0x140002463  mov     [rbp+1F0h+var_210], rcx
0x140002467  mov     [rbp+1F0h+var_1F4], ebx
0x14000246a  mov     [rbp+1F0h+var_218], 1
0x140002472  lea     rcx, [rax+8]
0x140002476  mov     [rbp+1F0h+var_228], 8
0x14000247e  mov     rax, [rax]
0x140002481  mov     [rbp+1F0h+var_240], rax
0x140002485  movzx   eax, word ptr [rcx]
0x140002488  mov     [rbp+1F0h+var_238], eax
0x14000248b  mov     rax, [rbp+1F0h+arg_40]
0x140002492  mov     [rbp+1F0h+var_250], rcx
0x140002496  mov     [rbp+1F0h+var_248], 2
0x14000249e  mov     [rbp+1F0h+var_234], ebx
0x1400024a1  mov     rcx, [rax]
0x1400024a4  mov     rax, [rbp+1F0h+arg_38]
0x1400024ab  mov     [rbp+1F0h+var_270], rax
0x1400024af  mov     rax, [rbp+1F0h+arg_30]
0x1400024b6  mov     [rsp+2F0h+var_280], rax
0x1400024bb  mov     rax, [rbp+1F0h+arg_28]
0x1400024c2  mov     [rsp+2F0h+var_290], rax
0x1400024c7  mov     rax, [rbp+1F0h+arg_20]
0x1400024ce  mov     [rsp+2F0h+var_2A0], rax
0x1400024d3  lea     rax, [rsp+2F0h+var_2C0]
0x1400024d8  mov     [rbp+1F0h+var_260], rcx
0x1400024dc  lea     rcx, dword_140029078
0x1400024e3  mov     [rsp+2F0h+var_2C8], rax
0x1400024e8  mov     [rsp+2F0h+var_2D0], 2Bh ; '+'
0x1400024f0  mov     [rbp+1F0h+var_258], 10h
0x1400024f8  mov     [rbp+1F0h+var_268], 1
0x140002500  mov     [rsp+2F0h+var_278], 4
0x140002509  mov     [rsp+2F0h+var_288], 4
0x140002512  mov     [rsp+2F0h+var_298], 8
0x14000251b  call    _tlgWriteTransfer_EventWriteTransfer
0x140002520  mov     rcx, [rbp+1F0h+var_10]
0x140002527  xor     rcx, rsp; StackCookie
0x14000252a  call    __security_check_cookie
0x14000252f  mov     rbx, [rsp+2F0h+arg_0]
0x140002537  add     rsp, 2F0h
0x14000253e  pop     rbp
0x14000253f  retn
```
