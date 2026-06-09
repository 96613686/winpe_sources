# ZtSetFiltersInstalled(HKEY__ *,int)

- ea: `0x1800553dc`
- end: `0x1800554d1`
- name: `?ZtSetFiltersInstalled@@YAJPEAUHKEY__@@H@Z`
- size: `245`
- prototype: `__int64 __fastcall(HKEY hKey, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800560e0`

## callees

- `0x180046ec0`
- `0x1800553dc`
- `0x1800554d8`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005543a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005543a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055482`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055482`

## string_xrefs

- `0x18005542c`: `ZtdnsFiltersInstalled`

## pseudocode

```c
__int64 __fastcall ZtSetFiltersInstalled(HKEY hKey, int a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  BYTE Data[8]; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)Data = a2;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 16, WPP_fc64c14ed7c530c8bb850137b0f0244d_Traceguids, hKey);
  if ( !hKey )
  {
    v4 = 87;
    goto LABEL_12;
  }
  if ( a2 )
  {
    v4 = RegSetValueExW(hKey, L"ZtdnsFiltersInstalled", 0, 4u, Data, 4u);
    if ( v4 )
      goto LABEL_12;
  }
  else
  {
    v5 = RegDeleteValueW(hKey, L"ZtdnsFiltersInstalled");
    v4 = v5;
    if ( v5 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 17, WPP_fc64c14ed7c530c8bb850137b0f0244d_Traceguids, v5);
      v4 = 0;
    }
  }
  ZtUpdateFiltersInstalled(a2);
LABEL_12:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 18, WPP_fc64c14ed7c530c8bb850137b0f0244d_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800553dc  mov     [rsp+arg_10], rbx
0x1800553e1  push    rdi
0x1800553e2  sub     rsp, 40h
0x1800553e6  mov     rax, cs:__security_cookie
0x1800553ed  xor     rax, rsp
0x1800553f0  mov     [rsp+48h+var_10], rax
0x1800553f5  mov     edi, edx
0x1800553f7  mov     dword ptr [rsp+48h+Data], edx
0x1800553fb  mov     rbx, rcx
0x1800553fe  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180055405  jz      short loc_180055420
0x180055407  mov     edx, 10h
0x18005540c  lea     r8, WPP_fc64c14ed7c530c8bb850137b0f0244d_Traceguids
0x180055413  mov     ecx, 40Bh
0x180055418  mov     r9, rbx
0x18005541b  call    WPP_SF_q
0x180055420  test    rbx, rbx
0x180055423  jnz     short loc_18005542C
0x180055425  mov     ebx, 57h ; 'W'
0x18005542a  jmp     short loc_180055495
0x18005542c  lea     rdx, aZtdnsfiltersin; "ZtdnsFiltersInstalled"
0x180055433  mov     rcx, rbx; hKey
0x180055436  test    edi, edi
0x180055438  jnz     short loc_18005546A
0x18005543a  call    cs:__imp_RegDeleteValueW
0x180055440  mov     ebx, eax
0x180055442  test    eax, eax
0x180055444  jz      short loc_18005548E
0x180055446  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005544d  jz      short loc_180055466
0x18005544f  lea     edx, [rdi+11h]
0x180055452  mov     ecx, 40Bh
0x180055457  mov     r9d, eax
0x18005545a  lea     r8, WPP_fc64c14ed7c530c8bb850137b0f0244d_Traceguids
0x180055461  call    WPP_SF_d
0x180055466  xor     ebx, ebx
0x180055468  jmp     short loc_18005548E
0x18005546a  mov     r9d, 4; dwType
0x180055470  lea     rax, [rsp+48h+Data]
0x180055475  mov     [rsp+48h+cbData], r9d; cbData
0x18005547a  xor     r8d, r8d; Reserved
0x18005547d  mov     [rsp+48h+lpData], rax; lpData
0x180055482  call    cs:__imp_RegSetValueExW
0x180055488  mov     ebx, eax
0x18005548a  test    eax, eax
0x18005548c  jnz     short loc_180055495
0x18005548e  mov     ecx, edi; int
0x180055490  call    ?ZtUpdateFiltersInstalled@@YAXH@Z; ZtUpdateFiltersInstalled(int)
0x180055495  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005549c  jz      short loc_1800554B7
0x18005549e  mov     edx, 12h
0x1800554a3  lea     r8, WPP_fc64c14ed7c530c8bb850137b0f0244d_Traceguids
0x1800554aa  mov     ecx, 40Bh
0x1800554af  mov     r9d, ebx
0x1800554b2  call    WPP_SF_d
0x1800554b7  mov     eax, ebx
0x1800554b9  mov     rcx, [rsp+48h+var_10]
0x1800554be  xor     rcx, rsp; StackCookie
0x1800554c1  call    __security_check_cookie
0x1800554c6  mov     rbx, [rsp+48h+arg_10]
0x1800554cb  add     rsp, 40h
0x1800554cf  pop     rdi
0x1800554d0  retn
```
