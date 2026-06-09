# CMediaClassData::GetAudioDeviceInstance(HKEY__ *,ushort const *,MEDIA_AUDIO_DEVICE_TYPE)

- ea: `0x18005823c`
- end: `0x1800585c3`
- name: `?GetAudioDeviceInstance@CMediaClassData@@AEAAJPEAUHKEY__@@PEBGW4MEDIA_AUDIO_DEVICE_TYPE@@@Z`
- size: `903`
- prototype: `int __high(HKEY, const unsigned __int16 *, enum MEDIA_AUDIO_DEVICE_TYPE)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800586b4`

## callees

- `0x180005e40`
- `0x18000fa50`
- `0x180013f50`
- `0x180014b80`
- `0x180017600`
- `0x1800321d4`
- `0x180057f40`
- `0x18005823c`
- `0x180058a04`
- `0x180058e00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800582dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800582dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058571`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058571`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMediaClassData::GetAudioDeviceInstance(__int64 *a1, HKEY a2, const WCHAR *a3, int a4)
{
  LSTATUS v6; // eax
  __int64 v7; // rcx
  signed int Value; // edi
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int128 *v11; // rdx
  __int128 *v12; // rdx
  __int64 v13; // r14
  __int64 v14; // r8
  __int64 v15; // rsi
  const wchar_t *v16; // rdx
  size_t v17; // r13
  const wchar_t *v18; // rcx
  size_t v19; // r8
  int v20; // eax
  __int64 v21; // rcx
  __int128 *v22; // rdx
  __int64 v23; // rsi
  HKEY hKey; // [rsp+30h] [rbp-138h] BYREF
  size_t v26; // [rsp+38h] [rbp-130h]
  _BYTE v27[16]; // [rsp+40h] [rbp-128h] BYREF
  __int64 v28; // [rsp+50h] [rbp-118h]
  wchar_t *S1[2]; // [rsp+58h] [rbp-110h] BYREF
  size_t N[2]; // [rsp+68h] [rbp-100h]
  __int128 v31; // [rsp+78h] [rbp-F0h] BYREF
  __m128i v32; // [rsp+88h] [rbp-E0h]
  _OWORD v33[2]; // [rsp+98h] [rbp-D0h] BYREF
  __int128 v34; // [rsp+B8h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+C8h] [rbp-A0h]
  __int128 v36; // [rsp+E0h] [rbp-88h] BYREF
  __m128i v37; // [rsp+F0h] [rbp-78h]
  _OWORD v38[2]; // [rsp+100h] [rbp-68h] BYREF

  v34 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v34) = 0;
  v33[0] = 0;
  v33[1] = si128;
  LOWORD(v33[0]) = 0;
  v31 = 0;
  v32 = si128;
  LOWORD(v31) = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(a2, a3, 0, 0x20019u, &hKey);
  Value = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      Value = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_44;
  }
  Value = CMediaClassData::QueryValue(v7, hKey, L"{b3f8fa53-0004-438e-9003-51a46e139bfc},2", &v34);
  if ( Value >= 0 )
  {
    Value = CMediaClassData::QueryValue(v9, hKey, L"{83da6326-97a6-4088-9453-a1923f573b29},3", v33);
    if ( Value >= 0 )
    {
      v11 = &v34;
      if ( si128.m128i_i64[1] > 7uLL )
        v11 = (__int128 *)v34;
      Value = CMediaClassData::MapMediaInterfaceToDeviceInstance(v10, v11, &v31);
      if ( Value >= 0 )
      {
        try
        {
          v12 = &v31;
          if ( v32.m128i_i64[1] > 7uLL )
            v12 = (__int128 *)v31;
          *(_OWORD *)S1 = 0;
          N[0] = 0;
          N[1] = 0;
          v13 = -1;
          v14 = -1;
          do
            ++v14;
          while ( *((_WORD *)v12 + v14) );
          std::wstring::_Construct<1,unsigned short const *>(S1, v12, v14);
          std::_Tree<std::_Tmap_traits<std::wstring,short,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,short>>,0>>::_Find_lower_bound<std::wstring>(
            a1,
            v27,
            S1);
          v15 = v28;
          if ( *(_BYTE *)(v28 + 25) )
            goto LABEL_25;
          v16 = (const wchar_t *)(v28 + 32);
          v17 = *(_QWORD *)(v28 + 48);
          if ( *(_QWORD *)(v28 + 56) > 7u )
            v16 = *(const wchar_t **)v16;
          v26 = N[0];
          v18 = (const wchar_t *)S1;
          if ( N[1] > 7 )
            v18 = S1[0];
          v19 = v17;
          if ( v17 >= N[0] )
            v19 = N[0];
          v20 = wmemcmp(v18, v16, v19);
          if ( v20 )
          {
            if ( v20 < 0 )
LABEL_25:
              v15 = *a1;
          }
          else if ( v26 < v17 )
          {
            goto LABEL_25;
          }
          std::wstring::~wstring(S1);
          if ( v15 == *a1 )
          {
            v36 = 0;
            v37 = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(v36) = 0;
            v38[0] = 0;
            v38[1] = v37;
            LOWORD(v38[0]) = 0;
            if ( a4 )
            {
              if ( a4 == 1 )
                std::wstring::operator=(v38, v33);
            }
            else
            {
              std::wstring::operator=(&v36, v33);
            }
            v22 = &v31;
            if ( v32.m128i_i64[1] > 7uLL )
              v22 = (__int128 *)v31;
            *(_OWORD *)S1 = 0;
            *(_OWORD *)N = 0;
            do
              ++v13;
            while ( *((_WORD *)v22 + v13) );
            std::wstring::_Construct<1,unsigned short const *>(S1, v22, v13);
            v23 = std::map<std::wstring,_MEDIA_DEVICE_INFO>::operator[](a1, S1);
            std::wstring::operator=(v23, &v36);
            std::wstring::operator=(v23 + 32, v38);
            std::wstring::~wstring(S1);
            std::wstring::~wstring(v38);
            std::wstring::~wstring(&v36);
            goto LABEL_42;
          }
          if ( a4 )
          {
            if ( a4 != 1 )
              goto LABEL_42;
            v21 = v15 + 96;
          }
          else
          {
            v21 = v15 + 64;
          }
          std::wstring::operator=(v21, v33);
        }
        catch ( std::bad_alloc )
        {
          LODWORD(v26) = -2147024888;
          Value = -2147024888;
        }
      }
    }
  }
LABEL_42:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_44:
  std::wstring::~wstring(&v31);
  std::wstring::~wstring(v33);
  std::wstring::~wstring(&v34);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x18005823c  push    rbx
0x18005823e  push    rsi
0x18005823f  push    rdi
0x180058240  push    r12
0x180058242  push    r13
0x180058244  push    r14
0x180058246  push    r15
0x180058248  sub     rsp, 130h
0x18005824f  mov     rax, cs:__security_cookie
0x180058256  xor     rax, rsp
0x180058259  mov     [rsp+168h+var_48], rax
0x180058261  mov     r15d, r9d
0x180058264  mov     r10, r8
0x180058267  mov     rax, rdx
0x18005826a  mov     r12, rcx
0x18005826d  xorps   xmm0, xmm0
0x180058270  movups  [rsp+168h+var_B0], xmm0
0x180058278  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180058280  movdqu  [rsp+168h+var_A0], xmm1
0x180058289  xor     ebx, ebx
0x18005828b  mov     word ptr [rsp+168h+var_B0], bx
0x180058293  movups  [rsp+168h+var_D0], xmm0
0x18005829b  movdqu  [rsp+168h+var_C0], xmm1
0x1800582a4  mov     word ptr [rsp+168h+var_D0], bx
0x1800582ac  movups  [rsp+168h+var_F0], xmm0
0x1800582b1  movdqu  [rsp+168h+var_E0], xmm1
0x1800582ba  mov     word ptr [rsp+168h+var_F0], bx
0x1800582bf  mov     [rsp+168h+hKey], rbx
0x1800582c4  lea     rcx, [rsp+168h+hKey]
0x1800582c9  mov     [rsp+168h+phkResult], rcx; phkResult
0x1800582ce  mov     r9d, 20019h; samDesired
0x1800582d4  xor     r8d, r8d; ulOptions
0x1800582d7  mov     rdx, r10; lpSubKey
0x1800582da  mov     rcx, rax; hKey
0x1800582dd  call    cs:__imp_RegOpenKeyExW
0x1800582e3  mov     edi, eax
0x1800582e5  test    eax, eax
0x1800582e7  jz      short loc_1800582FD
0x1800582e9  jle     loc_180058578
0x1800582ef  movzx   edi, ax
0x1800582f2  or      edi, 80070000h
0x1800582f8  jmp     loc_180058578
0x1800582fd  lea     r9, [rsp+168h+var_B0]
0x180058305  lea     r8, aB3f8fa53000443; "{b3f8fa53-0004-438e-9003-51a46e139bfc},"...
0x18005830c  mov     rdx, [rsp+168h+hKey]
0x180058311  call    ?QueryValue@CMediaClassData@@AEAAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CMediaClassData::QueryValue(HKEY__ *,ushort const *,std::wstring &)
0x180058316  mov     edi, eax
0x180058318  test    eax, eax
0x18005831a  js      loc_180058567
0x180058320  lea     r9, [rsp+168h+var_D0]
0x180058328  lea     r8, a83da632697a640; "{83da6326-97a6-4088-9453-a1923f573b29},"...
0x18005832f  mov     rdx, [rsp+168h+hKey]
0x180058334  call    ?QueryValue@CMediaClassData@@AEAAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CMediaClassData::QueryValue(HKEY__ *,ushort const *,std::wstring &)
0x180058339  mov     edi, eax
0x18005833b  test    eax, eax
0x18005833d  js      loc_180058567
0x180058343  lea     rdx, [rsp+168h+var_B0]
0x18005834b  cmp     qword ptr [rsp+168h+var_A0+8], 7
0x180058354  cmova   rdx, qword ptr [rsp+168h+var_B0]
0x18005835d  lea     r8, [rsp+168h+var_F0]
0x180058362  call    ?MapMediaInterfaceToDeviceInstance@CMediaClassData@@AEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CMediaClassData::MapMediaInterfaceToDeviceInstance(ushort const *,std::wstring &)
0x180058367  mov     edi, eax
0x180058369  test    eax, eax
0x18005836b  js      loc_180058567
0x180058371  lea     rdx, [rsp+168h+var_F0]
0x180058376  cmp     qword ptr [rsp+168h+var_E0+8], 7
0x18005837f  cmova   rdx, qword ptr [rsp+168h+var_F0]
0x180058385  xorps   xmm0, xmm0
0x180058388  movups  xmmword ptr [rsp+168h+S1], xmm0
0x18005838d  mov     [rsp+168h+N], rbx
0x180058392  mov     [rsp+168h+N+8], rbx
0x180058397  or      r14, 0FFFFFFFFFFFFFFFFh
0x18005839b  mov     r8, r14
0x18005839e  inc     r8
0x1800583a1  cmp     [rdx+r8*2], bx
0x1800583a6  jnz     short loc_18005839E
0x1800583a8  lea     rcx, [rsp+168h+S1]
0x1800583ad  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800583b2  lea     r8, [rsp+168h+S1]
0x1800583b7  lea     rdx, [rsp+168h+var_128]
0x1800583bc  mov     rcx, r12
0x1800583bf  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@FU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@F@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@F@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,short,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,short>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800583c4  mov     rsi, [rsp+168h+var_118]
0x1800583c9  cmp     [rsi+19h], bl
0x1800583cc  jnz     short loc_180058419
0x1800583ce  lea     rdx, [rsi+20h]
0x1800583d2  mov     r13, [rdx+10h]
0x1800583d6  cmp     qword ptr [rdx+18h], 7
0x1800583db  jbe     short loc_1800583E0
0x1800583dd  mov     rdx, [rdx]; S2
0x1800583e0  mov     rax, [rsp+168h+N]
0x1800583e5  mov     [rsp+168h+var_130], rax
0x1800583ea  lea     rcx, [rsp+168h+S1]
0x1800583ef  cmp     [rsp+168h+N+8], 7
0x1800583f5  cmova   rcx, [rsp+168h+S1]; S1
0x1800583fb  mov     r8, r13
0x1800583fe  cmp     r13, rax
0x180058401  cmovnb  r8, rax; N
0x180058405  call    wmemcmp
0x18005840a  test    eax, eax
0x18005840c  jnz     short loc_180058417
0x18005840e  cmp     [rsp+168h+var_130], r13
0x180058413  jnb     short loc_18005841D
0x180058415  jmp     short loc_180058419
0x180058417  jns     short loc_18005841D
0x180058419  mov     rsi, [r12]
0x18005841d  lea     rcx, [rsp+168h+S1]; void *
0x180058422  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058427  cmp     rsi, [r12]
0x18005842b  jz      short loc_180058458
0x18005842d  test    r15d, r15d
0x180058430  jnz     short loc_180058438
0x180058432  lea     rcx, [rsi+40h]
0x180058436  jmp     short loc_180058446
0x180058438  cmp     r15d, 1
0x18005843c  jnz     loc_180058561
0x180058442  lea     rcx, [rsi+60h]
0x180058446  lea     rdx, [rsp+168h+var_D0]
0x18005844e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180058453  jmp     loc_180058561
0x180058458  xorps   xmm0, xmm0
0x18005845b  movups  [rsp+168h+var_88], xmm0
0x180058463  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005846b  movdqa  [rsp+168h+var_78], xmm1
0x180058474  mov     word ptr [rsp+168h+var_88], bx
0x18005847c  movups  [rsp+168h+var_68], xmm0
0x180058484  movdqa  [rsp+168h+var_58], xmm1
0x18005848d  mov     word ptr [rsp+168h+var_68], bx
0x180058495  test    r15d, r15d
0x180058498  jnz     short loc_1800584B1
0x18005849a  lea     rdx, [rsp+168h+var_D0]
0x1800584a2  lea     rcx, [rsp+168h+var_88]
0x1800584aa  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800584af  jmp     short loc_1800584CC
0x1800584b1  cmp     r15d, 1
0x1800584b5  jnz     short loc_1800584CC
0x1800584b7  lea     rdx, [rsp+168h+var_D0]
0x1800584bf  lea     rcx, [rsp+168h+var_68]
0x1800584c7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800584cc  lea     rdx, [rsp+168h+var_F0]
0x1800584d1  cmp     qword ptr [rsp+168h+var_E0+8], 7
0x1800584da  cmova   rdx, qword ptr [rsp+168h+var_F0]
0x1800584e0  xorps   xmm0, xmm0
0x1800584e3  movups  xmmword ptr [rsp+168h+S1], xmm0
0x1800584e8  xorps   xmm1, xmm1
0x1800584eb  movdqu  xmmword ptr [rsp+168h+N], xmm1
0x1800584f1  inc     r14
0x1800584f4  cmp     [rdx+r14*2], bx
0x1800584f9  jnz     short loc_1800584F1
0x1800584fb  mov     r8, r14
0x1800584fe  lea     rcx, [rsp+168h+S1]
0x180058503  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180058508  nop
0x180058509  lea     rdx, [rsp+168h+S1]
0x18005850e  mov     rcx, r12
0x180058511  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_MEDIA_DEVICE_INFO@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_MEDIA_DEVICE_INFO@@@std@@@2@@std@@QEAAAEAU_MEDIA_DEVICE_INFO@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_MEDIA_DEVICE_INFO>::operator[](std::wstring &&)
0x180058516  mov     rsi, rax
0x180058519  lea     rdx, [rsp+168h+var_88]
0x180058521  mov     rcx, rax
0x180058524  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180058529  lea     rcx, [rsi+20h]
0x18005852d  lea     rdx, [rsp+168h+var_68]
0x180058535  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005853a  nop
0x18005853b  lea     rcx, [rsp+168h+S1]; void *
0x180058540  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058545  nop
0x180058546  lea     rcx, [rsp+168h+var_68]; void *
0x18005854e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058553  lea     rcx, [rsp+168h+var_88]; void *
0x18005855b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058560  nop
0x180058561  jmp     short loc_180058567
0x180058563  mov     edi, dword ptr [rsp+168h+var_130]
0x180058567  mov     rcx, [rsp+168h+hKey]; hKey
0x18005856c  test    rcx, rcx
0x18005856f  jz      short loc_180058578
0x180058571  call    cs:__imp_RegCloseKey
0x180058577  nop
0x180058578  lea     rcx, [rsp+168h+var_F0]; void *
0x18005857d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058582  nop
0x180058583  lea     rcx, [rsp+168h+var_D0]; void *
0x18005858b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058590  nop
0x180058591  lea     rcx, [rsp+168h+var_B0]; void *
0x180058599  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005859e  mov     eax, edi
0x1800585a0  mov     rcx, [rsp+168h+var_48]
0x1800585a8  xor     rcx, rsp; StackCookie
0x1800585ab  call    __security_check_cookie
0x1800585b0  add     rsp, 130h
0x1800585b7  pop     r15
0x1800585b9  pop     r14
0x1800585bb  pop     r13
0x1800585bd  pop     r12
0x1800585bf  pop     rdi
0x1800585c0  pop     rsi
0x1800585c1  pop     rbx
0x1800585c2  retn
```
