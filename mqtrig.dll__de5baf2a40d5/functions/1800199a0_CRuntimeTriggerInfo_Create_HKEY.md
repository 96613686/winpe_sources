# CRuntimeTriggerInfo::Create(HKEY__ *)

- ea: `0x1800199a0`
- end: `0x180019b43`
- name: `?Create@CRuntimeTriggerInfo@@QEAA_NPEAUHKEY__@@@Z`
- size: `419`
- prototype: `bool __fastcall(CRuntimeTriggerInfo *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180010590`

## callees

- `0x180004d88`
- `0x18000a2b8`
- `0x180012c84`
- `0x180014fc8`
- `0x1800199a0`
- `0x180019f58`
- `0x18001a15c`
- `0x18001e380`

## pseudocode

```c
bool __fastcall CRuntimeTriggerInfo::Create(CRuntimeTriggerInfo *this, HKEY a2)
{
  const wchar_t *v4; // r8
  _QWORD *v5; // rcx
  __int64 *v6; // rax
  __int64 v7; // rcx
  int v8; // eax
  bool result; // al
  HKEY TriggerKeyHandle; // [rsp+30h] [rbp-468h] BYREF
  HKEY v11; // [rsp+38h] [rbp-460h] BYREF
  HKEY v12[2]; // [rsp+40h] [rbp-458h] BYREF
  int v13; // [rsp+50h] [rbp-448h] BYREF
  wchar_t *v14; // [rsp+58h] [rbp-440h]
  __int64 v15; // [rsp+60h] [rbp-438h]
  int v16; // [rsp+68h] [rbp-430h]
  HKEY v17; // [rsp+70h] [rbp-428h]
  wchar_t v18[512]; // [rsp+80h] [rbp-418h] BYREF

  v12[1] = (HKEY)this;
  v4 = (const wchar_t *)*((_QWORD *)this + 260);
  if ( v4 )
    v4 = *(const wchar_t **)v4;
  TriggerKeyHandle = CRuntimeTriggerInfo::GetTriggerKeyHandle(this, a2, v4);
  if ( TriggerKeyHandle )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    goto LABEL_13;
  }
  v6 = (__int64 *)*((_QWORD *)this + 260);
  if ( v6 )
    v7 = *v6;
  else
    v7 = 0;
  v8 = StringCchPrintfW(v18, 0x1FFu, L"%s%s", (char *)this + 24, v7);
  v18[511] = 0;
  if ( v8 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
LABEL_13:
    WPP_SF_S(v5[2]);
LABEL_15:
    CRegHandle::~CRegHandle(&TriggerKeyHandle);
    return 0;
  }
  v13 = 1;
  v14 = v18;
  v15 = 0;
  v16 = 0;
  v17 = a2;
  try
  {
    v12[0] = CmCreateKey((const struct RegEntry *)&v13, 0x30003u);
    v11 = v12[0];
    CRuntimeTriggerInfo::FlushValuesToRegistry(this, &v11);
    CRegHandle::~CRegHandle(v12);
    CRegHandle::~CRegHandle(&TriggerKeyHandle);
    result = 1;
  }
  catch ( std::bad_alloc )
  {
    CmDeleteKey((const struct RegEntry *)&v13);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    goto LABEL_15;
  }
  v12[0] = CmCreateKey((const struct RegEntry *)&v13, 0x30003u);
}

```

## disassembly

```asm
0x1800199a0  mov     [rsp+arg_10], rbx
0x1800199a5  push    rdi
0x1800199a6  sub     rsp, 490h
0x1800199ad  mov     rax, cs:__security_cookie
0x1800199b4  xor     rax, rsp
0x1800199b7  mov     [rsp+498h+var_18], rax
0x1800199bf  mov     rdi, rdx
0x1800199c2  mov     rbx, rcx
0x1800199c5  mov     [rsp+498h+var_450], rcx
0x1800199ca  mov     r8, [rcx+820h]
0x1800199d1  test    r8, r8
0x1800199d4  jz      short loc_1800199D9
0x1800199d6  mov     r8, [r8]; wchar_t *
0x1800199d9  call    ?GetTriggerKeyHandle@CRuntimeTriggerInfo@@AEAAPEAUHKEY__@@PEAU2@PEB_W@Z; CRuntimeTriggerInfo::GetTriggerKeyHandle(HKEY__ *,wchar_t const *)
0x1800199de  mov     [rsp+498h+var_468], rax
0x1800199e3  test    rax, rax
0x1800199e6  jz      short loc_180019A24
0x1800199e8  lea     rax, WPP_GLOBAL_Control
0x1800199ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800199f6  cmp     rcx, rax
0x1800199f9  jz      loc_180019B16
0x1800199ff  test    byte ptr [rcx+1Ch], 1
0x180019a03  jz      loc_180019B16
0x180019a09  mov     rax, [rbx+820h]
0x180019a10  test    rax, rax
0x180019a13  jz      short loc_180019A1A
0x180019a15  mov     r9, [rax]
0x180019a18  jmp     short loc_180019A1D
0x180019a1a  xor     r9d, r9d
0x180019a1d  mov     edx, 13h
0x180019a22  jmp     short loc_180019AA1
0x180019a24  mov     rax, [rbx+820h]
0x180019a2b  test    rax, rax
0x180019a2e  jz      short loc_180019A35
0x180019a30  mov     rcx, [rax]
0x180019a33  jmp     short loc_180019A37
0x180019a35  xor     ecx, ecx
0x180019a37  lea     r9, [rbx+18h]
0x180019a3b  mov     [rsp+498h+var_478], rcx
0x180019a40  lea     r8, aSS_0; "%s%s"
0x180019a47  mov     edx, 1FFh; unsigned __int64
0x180019a4c  lea     rcx, [rsp+498h+var_418]; wchar_t *
0x180019a54  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180019a59  xor     ecx, ecx
0x180019a5b  mov     [rsp+498h+var_1A], cx
0x180019a63  test    eax, eax
0x180019a65  jns     short loc_180019AB3
0x180019a67  lea     rax, WPP_GLOBAL_Control
0x180019a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a75  cmp     rcx, rax
0x180019a78  jz      loc_180019B16
0x180019a7e  test    byte ptr [rcx+1Ch], 1
0x180019a82  jz      loc_180019B16
0x180019a88  mov     rax, [rbx+820h]
0x180019a8f  test    rax, rax
0x180019a92  jz      short loc_180019A99
0x180019a94  mov     r9, [rax]
0x180019a97  jmp     short loc_180019A9C
0x180019a99  xor     r9d, r9d
0x180019a9c  mov     edx, 14h
0x180019aa1  lea     r8, WPP_5d468cdb8ea734f7fb134a242ccb11b7_Traceguids
0x180019aa8  mov     rcx, [rcx+10h]; LoggerHandle
0x180019aac  call    WPP_SF_S
0x180019ab1  jmp     short loc_180019B16
0x180019ab3  mov     [rsp+498h+var_448], 1
0x180019abb  lea     rax, [rsp+498h+var_418]
0x180019ac3  mov     [rsp+498h+var_440], rax
0x180019ac8  mov     [rsp+498h+var_438], rcx
0x180019acd  mov     [rsp+498h+var_430], ecx
0x180019ad1  mov     [rsp+498h+var_428], rdi
0x180019ad6  mov     edx, 30003h; samDesired
0x180019adb  lea     rcx, [rsp+498h+var_448]; struct RegEntry *
0x180019ae0  call    ?CmCreateKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z; CmCreateKey(RegEntry const &,ulong)
0x180019ae5  mov     [rsp+498h+var_458], rax
0x180019aea  mov     [rsp+498h+var_460], rax
0x180019aef  lea     rdx, [rsp+498h+var_460]; HKEY *
0x180019af4  mov     rcx, rbx; this
0x180019af7  call    ?FlushValuesToRegistry@CRuntimeTriggerInfo@@AEAAXAEBQEAUHKEY__@@@Z; CRuntimeTriggerInfo::FlushValuesToRegistry(HKEY__ * const &)
0x180019afc  nop
0x180019afd  lea     rcx, [rsp+498h+var_458]; this
0x180019b02  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180019b07  nop
0x180019b08  lea     rcx, [rsp+498h+var_468]; this
0x180019b0d  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180019b12  mov     al, 1
0x180019b14  jmp     short loc_180019B22
0x180019b16  lea     rcx, [rsp+498h+var_468]; this
0x180019b1b  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180019b20  xor     al, al
0x180019b22  mov     rcx, [rsp+498h+var_18]
0x180019b2a  xor     rcx, rsp; StackCookie
0x180019b2d  call    __security_check_cookie
0x180019b32  mov     rbx, [rsp+498h+arg_10]
0x180019b3a  add     rsp, 490h
0x180019b41  pop     rdi
0x180019b42  retn
```
