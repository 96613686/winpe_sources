# RegDatabase::GetTable(__MIDL___MIDL_itf_estier3_0000_0000_0001,uint,tagFieldInfo * const,IEventObjectTable * *)

- ea: `0x180009200`
- end: `0x18000937c`
- name: `?GetTable@RegDatabase@@UEAAJW4__MIDL___MIDL_itf_estier3_0000_0000_0001@@IQEAUtagFieldInfo@@PEAPEAUIEventObjectTable@@@Z`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009200`
- `0x180009384`
- `0x180012654`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009339`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009339`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043829`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000923d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000923d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009283`

## string_xrefs

- `0x180009364`: `com\complus\src\events\Shared\UTSem.h`

## pseudocode

```c
__int64 __fastcall RegDatabase::GetTable(__int64 a1, unsigned int a2, int a3, __int64 a4, __int64 *a5)
{
  __int64 v6; // r14
  int v8; // r15d
  __int64 v9; // r12
  __int64 v10; // rbx
  __int64 v11; // rbx
  LPVOID v12; // rax
  _DWORD v14[3]; // [rsp+54h] [rbp-54h] BYREF
  __int64 v15; // [rsp+60h] [rbp-48h]
  __int64 v16; // [rsp+68h] [rbp-40h]
  unsigned __int8 v17; // [rsp+B8h] [rbp+10h]

  v6 = (int)a2;
  if ( a2 <= 2 )
  {
    v8 = 0;
    if ( !*(_DWORD *)(a1 + 80) )
      InternalAssert(L"com\\complus\\src\\events\\Shared\\UTSem.h", 0x12Eu, 0x10u, L"m_fInitialized");
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
    _mm_lfence();
    v9 = a1 + 8 * v6;
    v10 = *(_QWORD *)(v9 + 16);
    v15 = v10;
    if ( !v10 )
    {
      v11 = *(_QWORD *)(a1 + 8);
      v17 = *(_BYTE *)(a1 + 104);
      v16 = *(_QWORD *)(a1 + 96);
      v8 = 0;
      v14[0] = 0;
      v12 = CoTaskMemAlloc(0x298u);
      if ( v12 )
      {
        v10 = RegTable::RegTable(v12, v16, v17, a1 + 106, v6, a3, a4, v11, v14);
        v8 = v14[0];
      }
      else
      {
        v10 = 0;
      }
      v15 = v10;
      if ( v10 )
      {
        if ( v8 < 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          v10 = 0;
          v15 = 0;
        }
      }
      else
      {
        v8 = -2147024882;
        v14[0] = -2147024882;
      }
      v14[1] = v8;
      if ( v8 < 0 )
        goto LABEL_15;
      *(_QWORD *)(v9 + 16) = v10;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    *a5 = v10;
LABEL_15:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
    return (unsigned int)v8;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180009200  mov     [rsp+arg_10], r8d
0x180009205  mov     [rsp+arg_0], rcx
0x18000920a  push    rbx
0x18000920b  push    rsi
0x18000920c  push    rdi
0x18000920d  push    r12
0x18000920f  push    r13
0x180009211  push    r14
0x180009213  push    r15
0x180009215  sub     rsp, 70h
0x180009219  mov     r13, r9
0x18000921c  movsxd  r14, edx
0x18000921f  mov     rsi, rcx
0x180009222  cmp     r14d, 2
0x180009226  ja      loc_180009375
0x18000922c  xor     r15d, r15d
0x18000922f  cmp     [rcx+50h], r15d
0x180009233  jz      loc_180009352
0x180009239  lea     rcx, [rsi+28h]; lpCriticalSection
0x18000923d  call    cs:__imp_EnterCriticalSection
0x180009243  nop
0x180009244  lfence
0x180009247  lea     r12, [rsi+r14*8]
0x18000924b  mov     rbx, [r12+10h]
0x180009250  mov     [rsp+0A8h+var_48], rbx
0x180009255  test    rbx, rbx
0x180009258  jnz     loc_1800092FC
0x18000925e  mov     rbx, [rsi+8]
0x180009262  movzx   eax, byte ptr [rsi+68h]
0x180009266  mov     [rsp+0A8h+arg_8], al
0x18000926d  mov     rax, [rsi+60h]
0x180009271  mov     [rsp+0A8h+var_40], rax
0x180009276  xor     r15d, r15d
0x180009279  mov     [rsp+0A8h+var_54], r15d
0x18000927e  mov     ecx, 298h; cb
0x180009283  call    cs:__imp_CoTaskMemAlloc
0x180009289  test    rax, rax
0x18000928c  jnz     short loc_180009292
0x18000928e  xor     ebx, ebx
0x180009290  jmp     short loc_1800092D8
0x180009292  lea     r9, [rsi+6Ah]
0x180009296  lea     rcx, [rsp+0A8h+var_54]
0x18000929b  mov     [rsp+0A8h+var_68], rcx
0x1800092a0  mov     [rsp+0A8h+var_70], rbx
0x1800092a5  mov     [rsp+0A8h+var_78], r13
0x1800092aa  mov     ecx, [rsp+0A8h+arg_10]
0x1800092b1  mov     [rsp+0A8h+var_80], ecx
0x1800092b5  mov     [rsp+0A8h+var_88], r14d
0x1800092ba  movzx   r8d, [rsp+0A8h+arg_8]
0x1800092c3  mov     rdx, [rsp+0A8h+var_40]
0x1800092c8  mov     rcx, rax
0x1800092cb  call    ??0RegTable@@AEAA@PEAUHKEY__@@_NPEBGW4__MIDL___MIDL_itf_estier3_0000_0000_0001@@IQEAUtagFieldInfo@@2AEAJ@Z; RegTable::RegTable(HKEY__ *,bool,ushort const *,__MIDL___MIDL_itf_estier3_0000_0000_0001,uint,tagFieldInfo * const,ushort const *,long &)
0x1800092d0  mov     rbx, rax
0x1800092d3  mov     r15d, [rsp+0A8h+var_54]
0x1800092d8  mov     [rsp+0A8h+var_48], rbx
0x1800092dd  test    rbx, rbx
0x1800092e0  jnz     short loc_180009318
0x1800092e2  mov     r15d, 8007000Eh
0x1800092e8  mov     [rsp+0A8h+var_54], r15d
0x1800092ed  mov     [rsp+0A8h+var_50], r15d
0x1800092f2  test    r15d, r15d
0x1800092f5  js      short loc_180009335
0x1800092f7  mov     [r12+10h], rbx
0x1800092fc  mov     rax, [rbx]
0x1800092ff  mov     rcx, rbx
0x180009302  mov     rax, [rax+8]
0x180009306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000930b  mov     rdx, [rsp+0A8h+arg_20]
0x180009313  mov     [rdx], rbx
0x180009316  jmp     short loc_180009335
0x180009318  test    r15d, r15d
0x18000931b  jns     short loc_1800092ED
0x18000931d  mov     rax, [rbx]
0x180009320  mov     rcx, rbx
0x180009323  mov     rax, [rax+10h]
0x180009327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000932c  xor     ebx, ebx
0x18000932e  mov     [rsp+0A8h+var_48], rbx
0x180009333  jmp     short loc_1800092ED
0x180009335  lea     rcx, [rsi+28h]; lpCriticalSection
0x180009339  call    cs:__imp_LeaveCriticalSection
0x18000933f  mov     eax, r15d
0x180009342  add     rsp, 70h
0x180009346  pop     r15
0x180009348  pop     r14
0x18000934a  pop     r13
0x18000934c  pop     r12
0x18000934e  pop     rdi
0x18000934f  pop     rsi
0x180009350  pop     rbx
0x180009351  retn
0x180009352  mov     r8d, 10h; unsigned __int16
0x180009358  lea     r9, aMFinitialized; "m_fInitialized"
0x18000935f  mov     edx, 12Eh; unsigned int
0x180009364  lea     rcx, aComComplusSrcE_4; "com\\complus\\src\\events\\Shared\\UTSe"...
0x18000936b  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x180009370  jmp     loc_180009239
0x180009375  mov     eax, 80004005h
0x18000937a  jmp     short loc_180009342
0x180043810  push    rbp
0x180043812  sub     rsp, 50h
0x180043816  mov     rbp, rdx
0x180043819  mov     rcx, [rbp+0B0h]
0x180043820  add     rcx, 28h ; '('
0x180043824  add     rsp, 50h
0x180043828  pop     rbp
0x180043829  jmp     cs:__imp_LeaveCriticalSection
```
