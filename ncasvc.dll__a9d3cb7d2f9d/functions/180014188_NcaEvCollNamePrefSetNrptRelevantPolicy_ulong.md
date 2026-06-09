# NcaEvCollNamePrefSetNrptRelevantPolicy(ulong)

- ea: `0x180014188`
- end: `0x180014240`
- name: `?NcaEvCollNamePrefSetNrptRelevantPolicy@@YAKK@Z`
- size: `184`
- prototype: `__int64 __fastcall()`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180013eb0`
- `0x180013f60`
- `0x180014620`

## callees

- `0x1800037b0`
- `0x180004f34`
- `0x180014188`
- `0x180019784`
- `0x18001a00c`
- `0x18001ab04`

## string_xrefs

- `0x1800141af`: `SYSTEM\CurrentControlSet\Services\Dnscache\Parameters`

## pseudocode

```c
__int64 __fastcall NcaEvCollNamePrefSetNrptRelevantPolicy()
{
  int Key; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx

  Key = NcaRegCreateKey(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\Dnscache\\Parameters", 2u);
  if ( Key >= 0 )
  {
    Key = NcaRegSetDWord(0);
    if ( Key < 0 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v2 = 28;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = 27;
LABEL_9:
      WPP_SF_d(v1[2], v2, WPP_845cef01834031fc88ca7e3c296c903d_Traceguids, (unsigned int)Key);
    }
  }
  NcaRegCloseKey(0);
  return NcaHResultToWindowsError((unsigned int)Key);
}

```

## disassembly

```asm
0x180014188  mov     [rsp+arg_0], rbx
0x18001418d  push    rdi
0x18001418e  sub     rsp, 20h
0x180014192  mov     edi, ecx
0x180014194  mov     [rsp+28h+hKey], 0
0x18001419d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800141a4  lea     r9, [rsp+28h+hKey]
0x1800141a9  mov     r8d, 2; samDesired
0x1800141af  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x1800141b6  call    NcaRegCreateKey
0x1800141bb  mov     ebx, eax
0x1800141bd  test    eax, eax
0x1800141bf  jns     short loc_1800141E1
0x1800141c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141c8  lea     rax, WPP_GLOBAL_Control
0x1800141cf  cmp     rcx, rax
0x1800141d2  jz      short loc_180014225
0x1800141d4  test    byte ptr [rcx+1Ch], 1
0x1800141d8  jz      short loc_180014225
0x1800141da  mov     edx, 1Bh
0x1800141df  jmp     short loc_180014212
0x1800141e1  mov     rcx, [rsp+28h+hKey]; hKey
0x1800141e6  mov     r9d, edi
0x1800141e9  call    NcaRegSetDWord
0x1800141ee  mov     ebx, eax
0x1800141f0  test    eax, eax
0x1800141f2  jns     short loc_180014225
0x1800141f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141fb  lea     rax, WPP_GLOBAL_Control
0x180014202  cmp     rcx, rax
0x180014205  jz      short loc_180014225
0x180014207  test    byte ptr [rcx+1Ch], 1
0x18001420b  jz      short loc_180014225
0x18001420d  mov     edx, 1Ch
0x180014212  mov     rcx, [rcx+10h]
0x180014216  lea     r8, WPP_845cef01834031fc88ca7e3c296c903d_Traceguids
0x18001421d  mov     r9d, ebx
0x180014220  call    WPP_SF_d
0x180014225  mov     rcx, [rsp+28h+hKey]
0x18001422a  call    NcaRegCloseKey
0x18001422f  mov     ecx, ebx
0x180014231  mov     rbx, [rsp+28h+arg_0]
0x180014236  add     rsp, 20h
0x18001423a  pop     rdi
0x18001423b  jmp     NcaHResultToWindowsError
```
