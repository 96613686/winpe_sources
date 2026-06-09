# InitMachineNameOverride(void)

- ea: `0x1800146dc`
- end: `0x180014862`
- name: `?InitMachineNameOverride@@YAXXZ`
- size: `390`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001435c`

## callees

- `0x1800146dc`
- `0x18001ec30`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180014787`
- `msvcrt!wcsncpy_s` at `0x18001481f`
- `msvcrt!wcsncpy_s` at `0x180014787`
- `msvcrt!wcsncpy_s` at `0x18001481f`
- `KERNEL32!lstrlenW` at `0x180014739`
- `KERNEL32!lstrlenW` at `0x1800147aa`
- `KERNEL32!lstrlenW` at `0x180014739`
- `KERNEL32!lstrlenW` at `0x1800147aa`
- `KERNEL32!GetCommandLineW` at `0x180014703`
- `KERNEL32!GetCommandLineW` at `0x180014703`
- `KERNEL32!lstrcmpiW` at `0x18001475d`
- `KERNEL32!lstrcmpiW` at `0x1800147d2`
- `KERNEL32!lstrcmpiW` at `0x1800147fd`
- `KERNEL32!lstrcmpiW` at `0x18001475d`
- `KERNEL32!lstrcmpiW` at `0x1800147d2`
- `KERNEL32!lstrcmpiW` at `0x1800147fd`
- `KERNEL32!LocalFree` at `0x180014853`
- `KERNEL32!LocalFree` at `0x180014853`
- `SHELL32!CommandLineToArgvW` at `0x180014711`
- `SHELL32!CommandLineToArgvW` at `0x180014711`

## string_xrefs

- `0x1800147bd`: `/Computer=`

## pseudocode

```c
void InitMachineNameOverride(void)
{
  const WCHAR *CommandLineW; // rax
  LPWSTR *v1; // rdi
  int v2; // ebp
  LPWSTR v3; // rcx
  WCHAR v4; // bx
  int v5; // eax
  int v6; // edx
  LPWSTR v7; // rcx
  WCHAR v8; // bx
  LPWSTR v9; // rax
  int v10; // eax
  int v11; // edx
  int pNumArgs; // [rsp+50h] [rbp+8h] BYREF

  pNumArgs = 0;
  g_wszMachineNameOverride = 0;
  g_fMachineNameOverride = 0;
  g_wszAuxMessageSource = 0;
  CommandLineW = GetCommandLineW();
  v1 = CommandLineToArgvW(CommandLineW, &pNumArgs);
  if ( v1 )
  {
    v2 = 1;
    if ( pNumArgs > 1 )
    {
      while ( 1 )
      {
        if ( (unsigned int)lstrlenW(v1[v2]) > 0xB )
        {
          v3 = v1[v2];
          v4 = v3[11];
          v3[11] = 0;
          v5 = lstrcmpiW(v1[v2], L"/AuxSource=");
          v1[v2][11] = v4;
          if ( !v5 )
          {
            wcsncpy_s(&g_wszAuxMessageSource, 0x104u, v1[v2] + 11, 0xFFFFFFFFFFFFFFFFuLL);
            if ( (int)CanonicalizeComputername(&g_wszAuxMessageSource, v6) < 0 )
              g_wszAuxMessageSource = 0;
          }
        }
        if ( (unsigned int)lstrlenW(v1[v2]) <= 0xA )
          goto LABEL_13;
        v7 = v1[v2];
        v8 = v7[10];
        v7[10] = 0;
        if ( lstrcmpiW(v1[v2], L"/Computer=") )
          goto LABEL_13;
        v9 = v1[v2];
        g_fMachineNameOverride = 1;
        v9[10] = v8;
        v10 = lstrcmpiW(L"LocalMachine", v1[v2] + 10);
        if ( !v10 )
          goto LABEL_12;
        wcsncpy_s(&g_wszMachineNameOverride, 0x104u, v1[v2] + 10, 0xFFFFFFFFFFFFFFFFuLL);
        if ( (int)CanonicalizeComputername(&g_wszMachineNameOverride, v11) < 0 )
          break;
LABEL_13:
        if ( ++v2 >= pNumArgs )
          goto LABEL_14;
      }
      LOWORD(v10) = 0;
      g_fMachineNameOverride = 0;
LABEL_12:
      g_wszMachineNameOverride = v10;
      goto LABEL_13;
    }
LABEL_14:
    LocalFree(v1);
  }
}

```

## disassembly

```asm
0x1800146dc  push    rbx
0x1800146de  push    rbp
0x1800146df  push    rsi
0x1800146e0  push    rdi
0x1800146e1  sub     rsp, 28h
0x1800146e5  xor     eax, eax
0x1800146e7  mov     [rsp+48h+pNumArgs], 0
0x1800146ef  mov     cs:?g_wszMachineNameOverride@@3PAGA, ax; ushort near * g_wszMachineNameOverride
0x1800146f6  mov     cs:?g_fMachineNameOverride@@3HA, eax; int g_fMachineNameOverride
0x1800146fc  mov     cs:?g_wszAuxMessageSource@@3PAGA, ax; ushort near * g_wszAuxMessageSource
0x180014703  call    cs:__imp_GetCommandLineW
0x180014709  mov     rcx, rax; lpCmdLine
0x18001470c  lea     rdx, [rsp+48h+pNumArgs]; pNumArgs
0x180014711  call    cs:__imp_CommandLineToArgvW
0x180014717  mov     rdi, rax
0x18001471a  test    rax, rax
0x18001471d  jz      loc_180014859
0x180014723  mov     ebp, 1
0x180014728  cmp     [rsp+48h+pNumArgs], ebp
0x18001472c  jle     loc_180014850
0x180014732  movsxd  rsi, ebp
0x180014735  mov     rcx, [rdi+rsi*8]; lpString
0x180014739  call    cs:__imp_lstrlenW
0x18001473f  cmp     eax, 0Bh
0x180014742  jbe     short loc_1800147A6
0x180014744  mov     rcx, [rdi+rsi*8]
0x180014748  lea     rdx, g_szAuxMessageSourceSwitch; "/AuxSource="
0x18001474f  xor     eax, eax
0x180014751  movzx   ebx, word ptr [rcx+16h]
0x180014755  mov     [rcx+16h], ax
0x180014759  mov     rcx, [rdi+rsi*8]; lpString1
0x18001475d  call    cs:__imp_lstrcmpiW
0x180014763  mov     rcx, [rdi+rsi*8]
0x180014767  mov     [rcx+16h], bx
0x18001476b  test    eax, eax
0x18001476d  jnz     short loc_1800147A6
0x18001476f  mov     r8, [rdi+rsi*8]
0x180014773  lea     rcx, ?g_wszAuxMessageSource@@3PAGA; Destination
0x18001477a  add     r8, 16h; Source
0x18001477e  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180014782  mov     edx, 104h; SizeInWords
0x180014787  call    cs:__imp_wcsncpy_s
0x18001478d  lea     rcx, ?g_wszAuxMessageSource@@3PAGA; Destination
0x180014794  call    ?CanonicalizeComputername@@YAJPEAGH@Z; CanonicalizeComputername(ushort *,int)
0x180014799  test    eax, eax
0x18001479b  jns     short loc_1800147A6
0x18001479d  xor     eax, eax
0x18001479f  mov     cs:?g_wszAuxMessageSource@@3PAGA, ax; ushort near * g_wszAuxMessageSource
0x1800147a6  mov     rcx, [rdi+rsi*8]; lpString
0x1800147aa  call    cs:__imp_lstrlenW
0x1800147b0  cmp     eax, 0Ah
0x1800147b3  jbe     loc_180014844
0x1800147b9  mov     rcx, [rdi+rsi*8]
0x1800147bd  lea     rdx, g_szOverrideCommandLine; "/Computer="
0x1800147c4  xor     eax, eax
0x1800147c6  movzx   ebx, word ptr [rcx+14h]
0x1800147ca  mov     [rcx+14h], ax
0x1800147ce  mov     rcx, [rdi+rsi*8]; lpString1
0x1800147d2  call    cs:__imp_lstrcmpiW
0x1800147d8  test    eax, eax
0x1800147da  jnz     short loc_180014844
0x1800147dc  mov     rax, [rdi+rsi*8]
0x1800147e0  lea     rcx, g_szLocalMachine; "LocalMachine"
0x1800147e7  mov     cs:?g_fMachineNameOverride@@3HA, 1; int g_fMachineNameOverride
0x1800147f1  mov     [rax+14h], bx
0x1800147f5  mov     rdx, [rdi+rsi*8]
0x1800147f9  add     rdx, 14h; lpString2
0x1800147fd  call    cs:__imp_lstrcmpiW
0x180014803  test    eax, eax
0x180014805  jz      short loc_18001483D
0x180014807  mov     r8, [rdi+rsi*8]
0x18001480b  lea     rcx, ?g_wszMachineNameOverride@@3PAGA; Destination
0x180014812  add     r8, 14h; Source
0x180014816  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18001481a  mov     edx, 104h; SizeInWords
0x18001481f  call    cs:__imp_wcsncpy_s
0x180014825  lea     rcx, ?g_wszMachineNameOverride@@3PAGA; Destination
0x18001482c  call    ?CanonicalizeComputername@@YAJPEAGH@Z; CanonicalizeComputername(ushort *,int)
0x180014831  test    eax, eax
0x180014833  jns     short loc_180014844
0x180014835  xor     eax, eax
0x180014837  mov     cs:?g_fMachineNameOverride@@3HA, eax; int g_fMachineNameOverride
0x18001483d  mov     cs:?g_wszMachineNameOverride@@3PAGA, ax; ushort near * g_wszMachineNameOverride
0x180014844  inc     ebp
0x180014846  cmp     ebp, [rsp+48h+pNumArgs]
0x18001484a  jl      loc_180014732
0x180014850  mov     rcx, rdi; hMem
0x180014853  call    cs:__imp_LocalFree
0x180014859  add     rsp, 28h
0x18001485d  pop     rdi
0x18001485e  pop     rsi
0x18001485f  pop     rbp
0x180014860  pop     rbx
0x180014861  retn
```
