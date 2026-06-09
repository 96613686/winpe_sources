# CCrashSignature::LookupModuleInUnloadedModules(int *,ushort * const)

- ea: `0x180018358`
- end: `0x180018606`
- name: `?LookupModuleInUnloadedModules@CCrashSignature@@AEAAJPEAHQEAG@Z`
- size: `686`
- prototype: `__int64 __fastcall(CCrashSignature *__hidden this, int *, unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180017498`

## callees

- `0x1800028b4`
- `0x1800047cc`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x180016414`
- `0x1800180cc`
- `0x180018358`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018565`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001842d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001842d`

## pseudocode

```c
__int64 __fastcall CCrashSignature::LookupModuleInUnloadedModules(HANDLE *this, int *a2, unsigned __int16 *const a3)
{
  signed int ProcessUnloadedModulesInformation; // edi
  __int64 v7; // r14
  unsigned __int64 v8; // rax
  __int64 v9; // rsi
  char *v10; // rbx
  const struct std::nothrow_t *v11; // rdx
  __int64 v12; // r14
  unsigned __int64 v13; // r9
  char *v14; // r8
  char *v15; // rdi
  __int64 v16; // r8
  signed int LastError; // eax
  LPCVOID lpBaseAddress; // [rsp+30h] [rbp-38h] BYREF
  SIZE_T NumberOfBytesRead[6]; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v21; // [rsp+88h] [rbp+20h] BYREF

  *(_QWORD *)a3 = 0;
  lpBaseAddress = 0;
  NumberOfBytesRead[0] = 0;
  v21 = 0;
  ProcessUnloadedModulesInformation = CCrashSignature::GetProcessUnloadedModulesInformation(
                                        (CCrashSignature *)this,
                                        &v21,
                                        (struct _RTL_UNLOAD_EVENT_TRACE **)&lpBaseAddress);
  if ( ProcessUnloadedModulesInformation >= 0 )
  {
    v7 = v21;
    v8 = 104LL * v21;
    v9 = -1;
    if ( !is_mul_ok(v21, 0x68u) )
      v8 = -1;
    v10 = (char *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
    if ( v10 )
    {
      if ( ReadProcessMemory(this[1], lpBaseAddress, v10, 104 * v7, NumberOfBytesRead)
        && NumberOfBytesRead[0] == 104 * v7 )
      {
        if ( v21 )
        {
          v11 = 0;
          do
          {
            v12 = 104LL * (unsigned int)v11;
            v13 = *(_QWORD *)&v10[v12];
            if ( !v13 )
              break;
            v14 = (char *)this[45];
            if ( (unsigned __int64)v14 >= v13 && (unsigned __int64)v14 < v13 + *(_QWORD *)&v10[v12 + 8] )
            {
              *a2 = 1;
              this[43] = &v14[-v13];
              *(_WORD *)&v10[v12 + 90] = 0;
              *((_DWORD *)this + 68) = *(_DWORD *)&v10[v12 + 20];
              *((_DWORD *)this + 69) = *(_DWORD *)&v10[v12 + 8];
              v15 = &v10[v12 + 28];
              if ( v15 )
              {
                v16 = -1;
                do
                  ++v16;
                while ( *(_WORD *)&v15[2 * v16] );
              }
              else
              {
                v16 = 0;
              }
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                this + 25,
                &v10[v12 + 28],
                v16);
              if ( v15 )
              {
                do
                  ++v9;
                while ( *(_WORD *)&v15[2 * v9] );
              }
              else
              {
                v9 = 0;
              }
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                this + 29,
                &v10[v12 + 28],
                v9);
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                this + 29,
                L"_unloaded");
              *a3 = *(_WORD *)&v10[v12 + 94];
              a3[1] = *(_WORD *)&v10[v12 + 92];
              a3[2] = *(_WORD *)&v10[v12 + 98];
              a3[3] = *(_WORD *)&v10[v12 + 96];
              break;
            }
            v11 = (const struct std::nothrow_t *)(unsigned int)((_DWORD)v11 + 1);
          }
          while ( (unsigned int)v11 < v21 );
        }
        ProcessUnloadedModulesInformation = 0;
      }
      else
      {
        LastError = GetLastError();
        ProcessUnloadedModulesInformation = LastError;
        if ( LastError > 0 )
          ProcessUnloadedModulesInformation = (unsigned __int16)LastError | 0x80070000;
        if ( ProcessUnloadedModulesInformation >= 0 )
          ProcessUnloadedModulesInformation = -2147467259;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            &WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids,
            (unsigned int)ProcessUnloadedModulesInformation);
      }
      operator delete(v10, v11);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids,
      (unsigned int)ProcessUnloadedModulesInformation);
  }
  return (unsigned int)ProcessUnloadedModulesInformation;
}

```

## disassembly

```asm
0x180018358  mov     r11, rsp
0x18001835b  mov     [r11+8], rbx
0x18001835f  mov     [r11+10h], rbp
0x180018363  push    rsi
0x180018364  push    rdi
0x180018365  push    r12
0x180018367  push    r13
0x180018369  push    r14
0x18001836b  sub     rsp, 40h
0x18001836f  xor     ebx, ebx
0x180018371  xor     eax, eax
0x180018373  mov     [r8], rax
0x180018376  mov     r12, r8
0x180018379  mov     r13, rdx
0x18001837c  mov     [r11-38h], rbx
0x180018380  lea     r8, [r11-38h]; struct _RTL_UNLOAD_EVENT_TRACE **
0x180018384  mov     [r11-30h], rbx
0x180018388  lea     rdx, [r11+20h]; unsigned int *
0x18001838c  mov     [r11+20h], ebx
0x180018390  mov     rbp, rcx
0x180018393  call    ?GetProcessUnloadedModulesInformation@CCrashSignature@@AEAAJPEAKPEAPEAU_RTL_UNLOAD_EVENT_TRACE@@@Z; CCrashSignature::GetProcessUnloadedModulesInformation(ulong *,_RTL_UNLOAD_EVENT_TRACE * *)
0x180018398  mov     edi, eax
0x18001839a  test    eax, eax
0x18001839c  jns     short loc_1800183DA
0x18001839e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183a5  lea     rax, WPP_GLOBAL_Control
0x1800183ac  cmp     rcx, rax
0x1800183af  jz      loc_1800185ED
0x1800183b5  test    byte ptr [rcx+1Ch], 1
0x1800183b9  jz      loc_1800185ED
0x1800183bf  mov     rcx, [rcx+10h]
0x1800183c3  lea     edx, [rbx+18h]
0x1800183c6  mov     r9d, edi
0x1800183c9  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x1800183d0  call    WPP_SF_d
0x1800183d5  jmp     loc_1800185ED
0x1800183da  mov     r14d, [rsp+68h+arg_18]
0x1800183e2  mov     eax, 68h ; 'h'
0x1800183e7  mul     r14
0x1800183ea  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800183f1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800183f8  cmovb   rax, rsi
0x1800183fc  mov     rcx, rax; unsigned __int64
0x1800183ff  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018404  mov     rbx, rax
0x180018407  test    rax, rax
0x18001840a  jz      loc_1800185BF
0x180018410  mov     rdx, [rsp+68h+lpBaseAddress]; lpBaseAddress
0x180018415  lea     rax, [rsp+68h+NumberOfBytesRead]
0x18001841a  mov     rcx, [rbp+8]; hProcess
0x18001841e  mov     r8, rbx; lpBuffer
0x180018421  imul    rdi, r14, 68h ; 'h'
0x180018425  mov     [rsp+68h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18001842a  mov     r9, rdi; nSize
0x18001842d  call    cs:__imp_ReadProcessMemory
0x180018433  xor     r10d, r10d
0x180018436  test    eax, eax
0x180018438  jz      loc_180018565
0x18001843e  cmp     [rsp+68h+NumberOfBytesRead], rdi
0x180018443  jnz     loc_180018565
0x180018449  cmp     [rsp+68h+arg_18], r10d
0x180018451  jbe     loc_180018560
0x180018457  mov     edx, r10d
0x18001845a  mov     eax, edx
0x18001845c  imul    r14, rax, 68h ; 'h'
0x180018460  mov     r9, [r14+rbx]
0x180018464  test    r9, r9
0x180018467  jz      loc_180018560
0x18001846d  mov     r8, [rbp+168h]
0x180018474  cmp     r8, r9
0x180018477  jb      short loc_180018486
0x180018479  mov     rcx, [r14+rbx+8]
0x18001847e  add     rcx, r9
0x180018481  cmp     r8, rcx
0x180018484  jb      short loc_180018496
0x180018486  inc     edx
0x180018488  cmp     edx, [rsp+68h+arg_18]
0x18001848f  jb      short loc_18001845A
0x180018491  jmp     loc_180018560
0x180018496  sub     r8, r9
0x180018499  mov     dword ptr [r13+0], 1
0x1800184a1  mov     [rbp+158h], r8
0x1800184a8  lea     rdi, [rbx+1Ch]
0x1800184ac  mov     [r14+rbx+5Ah], r10w
0x1800184b2  lea     rcx, [rbp+0C8h]
0x1800184b9  mov     eax, [r14+rbx+14h]
0x1800184be  mov     [rbp+110h], eax
0x1800184c4  mov     eax, [r14+rbx+8]
0x1800184c9  mov     [rbp+114h], eax
0x1800184cf  add     rdi, r14
0x1800184d2  jz      short loc_1800184E3
0x1800184d4  mov     r8, rsi
0x1800184d7  inc     r8
0x1800184da  cmp     [rdi+r8*2], r10w
0x1800184df  jnz     short loc_1800184D7
0x1800184e1  jmp     short loc_1800184E6
0x1800184e3  mov     r8, r10
0x1800184e6  mov     rdx, rdi
0x1800184e9  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800184ee  xor     ecx, ecx
0x1800184f0  test    rdi, rdi
0x1800184f3  jz      short loc_180018500
0x1800184f5  inc     rsi
0x1800184f8  cmp     [rdi+rsi*2], cx
0x1800184fc  jnz     short loc_1800184F5
0x1800184fe  jmp     short loc_180018503
0x180018500  mov     rsi, rcx
0x180018503  mov     r8, rsi
0x180018506  lea     rcx, [rbp+0E8h]
0x18001850d  mov     rdx, rdi
0x180018510  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180018515  mov     r8d, 9
0x18001851b  lea     rdx, SubStr; "_unloaded"
0x180018522  lea     rcx, [rbp+0E8h]
0x180018529  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001852e  movzx   eax, word ptr [r14+rbx+5Eh]
0x180018534  xor     r10d, r10d
0x180018537  mov     [r12], ax
0x18001853c  movzx   eax, word ptr [r14+rbx+5Ch]
0x180018542  mov     [r12+2], ax
0x180018548  movzx   eax, word ptr [r14+rbx+62h]
0x18001854e  mov     [r12+4], ax
0x180018554  movzx   eax, word ptr [r14+rbx+60h]
0x18001855a  mov     [r12+6], ax
0x180018560  mov     edi, r10d
0x180018563  jmp     short loc_1800185B5
0x180018565  call    cs:__imp_GetLastError
0x18001856b  mov     edi, eax
0x18001856d  test    eax, eax
0x18001856f  jle     short loc_18001857A
0x180018571  movzx   edi, ax
0x180018574  or      edi, 80070000h
0x18001857a  test    edi, edi
0x18001857c  mov     eax, 80004005h
0x180018581  cmovns  edi, eax
0x180018584  mov     rcx, cs:WPP_GLOBAL_Control
0x18001858b  lea     rax, WPP_GLOBAL_Control
0x180018592  cmp     rcx, rax
0x180018595  jz      short loc_1800185B5
0x180018597  test    byte ptr [rcx+1Ch], 1
0x18001859b  jz      short loc_1800185B5
0x18001859d  mov     rcx, [rcx+10h]
0x1800185a1  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x1800185a8  mov     edx, 1Ah
0x1800185ad  mov     r9d, edi
0x1800185b0  call    WPP_SF_d
0x1800185b5  mov     rcx, rbx; void *
0x1800185b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800185bd  jmp     short loc_1800185ED
0x1800185bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185c6  lea     rax, WPP_GLOBAL_Control
0x1800185cd  cmp     rcx, rax
0x1800185d0  jz      short loc_1800185ED
0x1800185d2  test    byte ptr [rcx+1Ch], 1
0x1800185d6  jz      short loc_1800185ED
0x1800185d8  mov     rcx, [rcx+10h]
0x1800185dc  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x1800185e3  mov     edx, 19h
0x1800185e8  call    WPP_SF_
0x1800185ed  mov     rbx, [rsp+68h+arg_0]
0x1800185f2  mov     eax, edi
0x1800185f4  mov     rbp, [rsp+68h+arg_8]
0x1800185f9  add     rsp, 40h
0x1800185fd  pop     r14
0x1800185ff  pop     r13
0x180018601  pop     r12
0x180018603  pop     rdi
0x180018604  pop     rsi
0x180018605  retn
```
