# StartList::GetTempValue(ushort *,uint,ushort *,uint,ATL::CRegKey &)

- ea: `0x14001ed8c`
- end: `0x14001ef23`
- name: `?GetTempValue@StartList@@AEAAXPEAGI0IAEAVCRegKey@ATL@@@Z`
- size: `407`
- prototype: `void(StartList *__hidden this, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14001f728`

## callees

- `0x140007e90`
- `0x140009938`
- `0x140017644`
- `0x14001d250`
- `0x14001d298`
- `0x14001d3ac`
- `0x14001eb04`
- `0x14001ed8c`
- `0x140020e0c`
- `0x140025d42`

## string_xrefs

- `0x14001edc1`: `Software\Microsoft\Windows NT\CurrentVersion\AccessibilityTemp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall StartList::GetTempValue(
        StartList *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        HKEY *a6)
{
  int v9; // edx
  __int64 v10; // rcx
  __int64 Next; // rax
  const unsigned __int16 **v12; // rbx
  unsigned int v13; // r8d
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  unsigned __int16 *v16; // rcx
  _BYTE v17[352]; // [rsp+20h] [rbp-178h] BYREF
  __int64 v18; // [rsp+1A8h] [rbp+10h] BYREF
  unsigned int v19; // [rsp+1B0h] [rbp+18h] BYREF

  v19 = a3;
  *a2 = 0;
  *a4 = 0;
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)a6,
                        HKEY_CURRENT_USER,
                        L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AccessibilityTemp",
                        0x2001Fu) )
  {
    v19 = 0;
    ATManager::ATManager((ATManager *)v17, v9);
    v10 = *(_QWORD *)ATManager::GetAccommodations(v17);
    v18 = v10;
    while ( v18 )
    {
      Next = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
               v10,
               &v18);
      v12 = *(const unsigned __int16 ***)Next;
      if ( wcscmp_0(*(const wchar_t **)(*(_QWORD *)Next + 40LL), L"SystemSetting") )
      {
        if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)a6, *v12, &v19) )
        {
          v13 = v19;
          if ( (v19 & 2) != 0 )
          {
            *((_DWORD *)this + 74) = 1;
            v19 = v13 & 0xFFFFFFFD;
            ATL::CRegKey::SetDWORDValue(a6, *v12, v13 & 0xFFFFFFFD);
            v15 = -1;
            if ( (v19 & 1) != 0 )
            {
              do
                ++v15;
              while ( a2[v15] );
              if ( v15 )
                StringCbCatW(a2, v14, L",");
              v16 = a2;
            }
            else
            {
              do
                ++v15;
              while ( a4[v15] );
              if ( v15 )
                StringCbCatW(a4, v14, L",");
              v16 = a4;
            }
            StringCbCatW(v16, v14, *v12);
          }
        }
      }
    }
    ATManager::~ATManager((ATManager *)v17);
  }
}

```

## disassembly

```asm
0x14001ed8c  mov     [rsp+arg_0], rbx
0x14001ed91  mov     [rsp+arg_18], rsi
0x14001ed96  mov     [rsp+arg_10], r8d
0x14001ed9b  push    rdi
0x14001ed9c  push    r14
0x14001ed9e  push    r15
0x14001eda0  sub     rsp, 180h
0x14001eda7  mov     rdi, r9
0x14001edaa  mov     rsi, rdx
0x14001edad  mov     r14, rcx
0x14001edb0  xor     r15d, r15d
0x14001edb3  mov     [rdx], r15w
0x14001edb7  mov     [r9], r15w
0x14001edbb  mov     r9d, 2001Fh; unsigned int
0x14001edc1  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001edc8  mov     rdx, 0FFFFFFFF80000001h; hKey
0x14001edcf  mov     rcx, [rsp+198h+arg_28]; this
0x14001edd7  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001eddc  test    eax, eax
0x14001edde  jnz     loc_14001EF0A
0x14001ede4  mov     [rsp+198h+arg_10], r15d
0x14001edec  lea     rcx, [rsp+198h+var_178]; this
0x14001edf1  call    ??0ATManager@@QEAA@H@Z; ATManager::ATManager(int)
0x14001edf6  nop
0x14001edf7  lea     rcx, [rsp+198h+var_178]
0x14001edfc  call    ?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ; ATManager::GetAccommodations(void)
0x14001ee01  mov     rcx, [rax]
0x14001ee04  mov     [rsp+198h+arg_8], rcx
0x14001ee0c  test    rcx, rcx
0x14001ee0f  jz      loc_14001EF00
0x14001ee15  lea     rdx, [rsp+198h+arg_8]
0x14001ee1d  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x14001ee22  nop
0x14001ee23  mov     rbx, [rax]
0x14001ee26  lea     rdx, aSystemsetting; "SystemSetting"
0x14001ee2d  mov     rcx, [rbx+28h]; String1
0x14001ee31  call    wcscmp_0
0x14001ee36  nop
0x14001ee37  test    eax, eax
0x14001ee39  jz      loc_14001EEF2
0x14001ee3f  lea     r8, [rsp+198h+arg_10]; unsigned int *
0x14001ee47  mov     rdx, [rbx]; unsigned __int16 *
0x14001ee4a  mov     rcx, [rsp+198h+arg_28]; this
0x14001ee52  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x14001ee57  test    eax, eax
0x14001ee59  jnz     loc_14001EEF2
0x14001ee5f  mov     r8d, [rsp+198h+arg_10]
0x14001ee67  test    r8b, 2
0x14001ee6b  jz      loc_14001EEF2
0x14001ee71  mov     dword ptr [r14+128h], 1
0x14001ee7c  and     r8d, 0FFFFFFFDh; unsigned int
0x14001ee80  mov     [rsp+198h+arg_10], r8d
0x14001ee88  mov     rdx, [rbx]; unsigned __int16 *
0x14001ee8b  mov     rcx, [rsp+198h+arg_28]; this
0x14001ee93  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x14001ee98  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001ee9c  test    byte ptr [rsp+198h+arg_10], 1
0x14001eea4  jz      short loc_14001EEC9
0x14001eea6  inc     rax
0x14001eea9  cmp     [rsi+rax*2], r15w
0x14001eeae  jnz     short loc_14001EEA6
0x14001eeb0  test    rax, rax
0x14001eeb3  jz      short loc_14001EEC4
0x14001eeb5  lea     r8, asc_14002C214; ","
0x14001eebc  mov     rcx, rsi; unsigned __int16 *
0x14001eebf  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14001eec4  mov     rcx, rsi
0x14001eec7  jmp     short loc_14001EEEA
0x14001eec9  inc     rax
0x14001eecc  cmp     [rdi+rax*2], r15w
0x14001eed1  jnz     short loc_14001EEC9
0x14001eed3  test    rax, rax
0x14001eed6  jz      short loc_14001EEE7
0x14001eed8  lea     r8, asc_14002C214; ","
0x14001eedf  mov     rcx, rdi; unsigned __int16 *
0x14001eee2  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14001eee7  mov     rcx, rdi; unsigned __int16 *
0x14001eeea  mov     r8, [rbx]; unsigned __int16 *
0x14001eeed  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14001eef2  cmp     [rsp+198h+arg_8], r15
0x14001eefa  jnz     loc_14001EE15
0x14001ef00  lea     rcx, [rsp+198h+var_178]; this
0x14001ef05  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x14001ef0a  lea     r11, [rsp+198h+var_18]
0x14001ef12  mov     rbx, [r11+20h]
0x14001ef16  mov     rsi, [r11+38h]
0x14001ef1a  mov     rsp, r11
0x14001ef1d  pop     r15
0x14001ef1f  pop     r14
0x14001ef21  pop     rdi
0x14001ef22  retn
```
