# DwMarkInterfaceKeyAsVPN(ushort *,ushort *,ulong)

- ea: `0x18006dc50`
- end: `0x18006de65`
- name: `?DwMarkInterfaceKeyAsVPN@@YAKPEAG0K@Z`
- size: `533`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18006c404`

## callees

- `0x180028058`
- `0x18006dc50`
- `0x18006e34c`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18006ddba`
- `ADVAPI32!RegSetValueExW` at `0x18006ddba`
- `ADVAPI32!RegOpenKeyExW` at `0x18006dd86`
- `ADVAPI32!RegOpenKeyExW` at `0x18006dd86`
- `ADVAPI32!RegCloseKey` at `0x18006de05`
- `ADVAPI32!RegCloseKey` at `0x18006de05`

## string_xrefs

- `0x18006dcdf`: `DwMarkInterfaceKeyAsVPN : Call to StringCchCopyW returned error`
- `0x18006dcfd`: `DwMarkInterfaceKeyAsVPN : Call to StringCchCopyW returned error`
- `0x18006de13`: `DwMarkInterfaceKeyAsVPN : Failed to Open the Registry Key`
- `0x18006de2d`: `DwMarkInterfaceKeyAsVPN : Failed to Open the Registry Key`

## pseudocode

```c
__int64 __fastcall DwMarkInterfaceKeyAsVPN(unsigned __int16 *a1, char *a2, unsigned int a3)
{
  __int64 v5; // r9
  WCHAR *v6; // r8
  WCHAR v7; // ax
  WCHAR *v8; // rax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  const wchar_t *v11; // r8
  __int64 v12; // rax
  __int64 v13; // rcx
  BYTE Data[8]; // [rsp+30h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-240h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-238h] BYREF

  *(_DWORD *)Data = 1;
  hKey = 0;
  v5 = 260;
  v6 = SubKey;
  do
  {
    if ( v5 == -2147483386 )
      break;
    v7 = *(WCHAR *)((char *)v6 + a2 - (char *)SubKey);
    if ( !v7 )
      break;
    *v6++ = v7;
    --v5;
  }
  while ( v5 );
  v8 = v6 - 1;
  if ( v5 )
    v8 = v6;
  *v8 = 0;
  v9 = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
  {
    v12 = -1;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&a2[2 * v13] );
    do
      ++v12;
    while ( a1[v12] );
    v9 = StringCchCatW(SubKey, v13 + v12 + 1, a1);
    if ( v9 )
    {
      TraceIt(a3, "DwMarkInterfaceKeyAsVPN : Call to StringCchCatW returned error");
      v10 = xmmword_1800D1020;
      if ( (_QWORD)xmmword_1800D1020 )
      {
        v11 = L"DwMarkInterfaceKeyAsVPN : Call to StringCchCatW returned error";
        goto LABEL_23;
      }
    }
    else
    {
      v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &hKey);
      if ( v9 )
      {
        TraceIt(a3, "DwMarkInterfaceKeyAsVPN : Failed to Open the Registry Key");
        v10 = xmmword_1800D1020;
        if ( (_QWORD)xmmword_1800D1020 )
        {
          v11 = L"DwMarkInterfaceKeyAsVPN : Failed to Open the Registry Key";
          goto LABEL_23;
        }
      }
      else
      {
        v9 = RegSetValueExW(hKey, L"VPNInterface", 0, 4u, Data, 4u);
        if ( v9 )
        {
          TraceIt(a3, "DwMarkInterfaceKeyAsVPN : Failed to set the flag VPNInterface to 1");
          if ( (_QWORD)xmmword_1800D1020 )
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRegHelpTemplateFunc)(
              gRegHelpEtwContext,
              xmmword_1800D1020,
              L"DwMarkInterfaceKeyAsVPN : Failed to set the flag VPNInterface to 1");
        }
        RegCloseKey(hKey);
      }
    }
  }
  else
  {
    TraceIt(a3, "DwMarkInterfaceKeyAsVPN : Call to StringCchCopyW returned error");
    v10 = xmmword_1800D1020;
    if ( (_QWORD)xmmword_1800D1020 )
    {
      v11 = L"DwMarkInterfaceKeyAsVPN : Call to StringCchCopyW returned error";
LABEL_23:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRegHelpTemplateFunc)(gRegHelpEtwContext, v10, v11);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18006dc50  push    rbx
0x18006dc52  push    rsi
0x18006dc53  push    rdi
0x18006dc54  sub     rsp, 260h
0x18006dc5b  mov     rax, cs:__security_cookie
0x18006dc62  xor     rax, rsp
0x18006dc65  mov     [rsp+278h+var_28], rax
0x18006dc6d  mov     r10, rcx
0x18006dc70  mov     dword ptr [rsp+278h+Data], 1
0x18006dc78  xor     esi, esi
0x18006dc7a  lea     rax, [rsp+278h+SubKey]
0x18006dc7f  mov     rcx, rdx
0x18006dc82  mov     [rsp+278h+hKey], rsi
0x18006dc87  mov     edi, r8d
0x18006dc8a  sub     rcx, rax
0x18006dc8d  mov     r9d, 104h
0x18006dc93  lea     r8, [rsp+278h+SubKey]
0x18006dc98  lea     rax, [r9+7FFFFEFAh]
0x18006dc9f  test    rax, rax
0x18006dca2  jz      short loc_18006DCBC
0x18006dca4  movzx   eax, word ptr [rcx+r8]
0x18006dca9  test    ax, ax
0x18006dcac  jz      short loc_18006DCBC
0x18006dcae  mov     [r8], ax
0x18006dcb2  add     r8, 2
0x18006dcb6  sub     r9, 1
0x18006dcba  jnz     short loc_18006DC98
0x18006dcbc  test    r9, r9
0x18006dcbf  lea     rax, [r8-2]
0x18006dcc3  cmovnz  rax, r8
0x18006dcc7  mov     [rax], si
0x18006dcca  mov     rax, r9
0x18006dccd  neg     rax
0x18006dcd0  sbb     ebx, ebx
0x18006dcd2  not     ebx
0x18006dcd4  and     ebx, 8007007Ah
0x18006dcda  test    r9, r9
0x18006dcdd  jnz     short loc_18006DD09
0x18006dcdf  lea     rdx, aDwmarkinterfac_5; "DwMarkInterfaceKeyAsVPN : Call to Strin"...
0x18006dce6  mov     ecx, edi; unsigned int
0x18006dce8  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006dced  mov     rdx, qword ptr cs:xmmword_1800D1020
0x18006dcf4  test    rdx, rdx
0x18006dcf7  jz      loc_18006DE47
0x18006dcfd  lea     r8, aDwmarkinterfac_7; "DwMarkInterfaceKeyAsVPN : Call to Strin"...
0x18006dd04  jmp     loc_18006DE34
0x18006dd09  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006dd0d  mov     rcx, rax
0x18006dd10  inc     rcx
0x18006dd13  cmp     [rdx+rcx*2], si
0x18006dd17  jnz     short loc_18006DD10
0x18006dd19  inc     rax
0x18006dd1c  cmp     [r10+rax*2], si
0x18006dd21  jnz     short loc_18006DD19
0x18006dd23  lea     rdx, [rax+1]
0x18006dd27  mov     r8, r10; unsigned __int16 *
0x18006dd2a  add     rdx, rcx; unsigned __int64
0x18006dd2d  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x18006dd32  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006dd37  mov     ebx, eax
0x18006dd39  test    eax, eax
0x18006dd3b  jz      short loc_18006DD67
0x18006dd3d  lea     rdx, aDwmarkinterfac_1; "DwMarkInterfaceKeyAsVPN : Call to Strin"...
0x18006dd44  mov     ecx, edi; unsigned int
0x18006dd46  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006dd4b  mov     rdx, qword ptr cs:xmmword_1800D1020
0x18006dd52  test    rdx, rdx
0x18006dd55  jz      loc_18006DE47
0x18006dd5b  lea     r8, aDwmarkinterfac; "DwMarkInterfaceKeyAsVPN : Call to Strin"...
0x18006dd62  jmp     loc_18006DE34
0x18006dd67  lea     rax, [rsp+278h+hKey]
0x18006dd6c  mov     r9d, 20006h; samDesired
0x18006dd72  xor     r8d, r8d; ulOptions
0x18006dd75  mov     [rsp+278h+phkResult], rax; phkResult
0x18006dd7a  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x18006dd7f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006dd86  call    cs:__imp_RegOpenKeyExW
0x18006dd8d  nop     dword ptr [rax+rax+00h]
0x18006dd92  mov     ebx, eax
0x18006dd94  test    eax, eax
0x18006dd96  jnz     short loc_18006DE13
0x18006dd98  mov     rcx, [rsp+278h+hKey]; hKey
0x18006dd9d  lea     r9d, [rax+4]; dwType
0x18006dda1  lea     rax, [rsp+278h+Data]
0x18006dda6  mov     [rsp+278h+cbData], r9d; cbData
0x18006ddab  xor     r8d, r8d; Reserved
0x18006ddae  mov     [rsp+278h+phkResult], rax; lpData
0x18006ddb3  lea     rdx, aVpninterface; "VPNInterface"
0x18006ddba  call    cs:__imp_RegSetValueExW
0x18006ddc1  nop     dword ptr [rax+rax+00h]
0x18006ddc6  mov     ebx, eax
0x18006ddc8  test    eax, eax
0x18006ddca  jz      short loc_18006DE00
0x18006ddcc  lea     rdx, aDwmarkinterfac_8; "DwMarkInterfaceKeyAsVPN : Failed to set"...
0x18006ddd3  mov     ecx, edi; unsigned int
0x18006ddd5  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006ddda  mov     rdx, qword ptr cs:xmmword_1800D1020
0x18006dde1  test    rdx, rdx
0x18006dde4  jz      short loc_18006DE00
0x18006dde6  mov     rcx, cs:gRegHelpEtwContext
0x18006dded  lea     r8, aDwmarkinterfac_3; "DwMarkInterfaceKeyAsVPN : Failed to set"...
0x18006ddf4  mov     rax, cs:gRegHelpTemplateFunc
0x18006ddfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de00  mov     rcx, [rsp+278h+hKey]; hKey
0x18006de05  call    cs:__imp_RegCloseKey
0x18006de0c  nop     dword ptr [rax+rax+00h]
0x18006de11  jmp     short loc_18006DE47
0x18006de13  lea     rdx, aDwmarkinterfac_6; "DwMarkInterfaceKeyAsVPN : Failed to Ope"...
0x18006de1a  mov     ecx, edi; unsigned int
0x18006de1c  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006de21  mov     rdx, qword ptr cs:xmmword_1800D1020
0x18006de28  test    rdx, rdx
0x18006de2b  jz      short loc_18006DE47
0x18006de2d  lea     r8, aDwmarkinterfac_2; "DwMarkInterfaceKeyAsVPN : Failed to Ope"...
0x18006de34  mov     rcx, cs:gRegHelpEtwContext
0x18006de3b  mov     rax, cs:gRegHelpTemplateFunc
0x18006de42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de47  mov     eax, ebx
0x18006de49  mov     rcx, [rsp+278h+var_28]
0x18006de51  xor     rcx, rsp; StackCookie
0x18006de54  call    __security_check_cookie
0x18006de59  add     rsp, 260h
0x18006de60  pop     rdi
0x18006de61  pop     rsi
0x18006de62  pop     rbx
0x18006de63  retn
```
