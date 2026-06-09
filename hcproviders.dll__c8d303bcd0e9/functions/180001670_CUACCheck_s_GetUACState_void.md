# CUACCheck::s_GetUACState(void)

- ea: `0x180001670`
- end: `0x1800018ba`
- name: `?s_GetUACState@CUACCheck@@CA?AW4UACSTATE@1@XZ`
- size: `586`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001320`
- `0x1800015b0`

## callees

- `0x180001670`
- `0x1800018c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800016be`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001784`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800017e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800016be`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180001784`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800017e0`
- `KERNEL32!CheckElevationEnabled` at `0x1800016e1`
- `KERNEL32!CheckElevationEnabled` at `0x1800016e1`

## pseudocode

```c
__int64 CUACCheck::s_GetUACState()
{
  unsigned int v0; // ebx
  LSTATUS ValueW; // eax
  bool v2; // sf
  bool v3; // al
  const WCHAR *v4; // r8
  LSTATUS v5; // eax
  bool v6; // sf
  LSTATUS v7; // eax
  bool v8; // sf
  DWORD v9; // ecx
  DWORD v11[10]; // [rsp+40h] [rbp-28h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp+8h] BYREF
  int pvData; // [rsp+78h] [rbp+10h] BYREF
  DWORD v14; // [rsp+80h] [rbp+18h] BYREF
  int v15; // [rsp+88h] [rbp+20h] BYREF

  pcbData = 4;
  pvData = 0;
  v0 = 6;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
             L"EnableLUA",
             0x10u,
             0,
             &pvData,
             &pcbData);
  v2 = ValueW < 0;
  if ( ValueW > 0 )
    v2 = 1;
  if ( !v2 )
  {
    pcbData = 0;
    v3 = !(unsigned int)CheckElevationEnabled(&pcbData) && pcbData;
    if ( pvData )
    {
      if ( v3 )
      {
        pcbData = 0;
        if ( (UserIsUACAdmin((PBOOL)&pcbData) & 0x80000000) == 0 )
        {
          v4 = L"ConsentPromptBehaviorAdmin";
          v15 = 0;
          if ( !pcbData )
            v4 = L"ConsentPromptBehaviorUser";
          v14 = 4;
          v5 = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
                 v4,
                 0x10u,
                 0,
                 &v15,
                 &v14);
          v6 = v5 < 0;
          if ( v5 > 0 )
            v6 = 1;
          if ( !v6 )
          {
            v14 = 0;
            v11[0] = 4;
            v7 = RegGetValueW(
                   HKEY_LOCAL_MACHINE,
                   L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
                   L"PromptOnSecureDesktop",
                   0x10u,
                   0,
                   &v14,
                   v11);
            v8 = v7 < 0;
            if ( v7 > 0 )
              v8 = 1;
            if ( v8 )
              v9 = 0;
            else
              v9 = v14;
            if ( v15 )
            {
              switch ( v15 )
              {
                case 5:
                  return 4;
                case 1:
                  return 1;
                case 2:
                  return 0;
                case 3:
                  v0 = 3;
                  if ( v9 )
                    return 1;
                  break;
                case 4:
                  v0 = 2;
                  if ( v9 )
                    return 0;
                  break;
              }
            }
            else
            {
              return 5;
            }
          }
        }
      }
      else
      {
        return 7;
      }
    }
    else
    {
      return 2 * (unsigned int)v3 + 6;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180001670  push    rbx
0x180001672  push    rdi
0x180001673  sub     rsp, 58h
0x180001677  lea     rax, [rsp+68h+arg_0]
0x18000167c  mov     [rsp+68h+arg_0], 4
0x180001684  mov     [rsp+68h+pcbData], rax; pcbData
0x180001689  lea     r8, Value; "EnableLUA"
0x180001690  lea     rax, [rsp+68h+arg_8]
0x180001695  xor     edi, edi
0x180001697  mov     [rsp+68h+pvData], rax; pvData
0x18000169c  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800016a3  mov     r9d, 10h; dwFlags
0x1800016a9  mov     [rsp+68h+pdwType], rdi; pdwType
0x1800016ae  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800016b5  mov     [rsp+68h+arg_8], edi
0x1800016b9  mov     ebx, 6
0x1800016be  call    cs:__imp_RegGetValueW
0x1800016c5  nop     dword ptr [rax+rax+00h]
0x1800016ca  test    eax, eax
0x1800016cc  jg      loc_18000184E
0x1800016d2  js      loc_180001816
0x1800016d8  lea     rcx, [rsp+68h+arg_0]
0x1800016dd  mov     [rsp+68h+arg_0], edi
0x1800016e1  call    cs:__imp_CheckElevationEnabled
0x1800016e8  nop     dword ptr [rax+rax+00h]
0x1800016ed  test    eax, eax
0x1800016ef  jnz     loc_180001820
0x1800016f5  cmp     [rsp+68h+arg_0], edi
0x1800016f9  jz      loc_180001820
0x1800016ff  mov     al, 1
0x180001701  cmp     [rsp+68h+arg_8], edi
0x180001705  jz      loc_18000185D
0x18000170b  test    al, al
0x18000170d  jz      loc_180001869
0x180001713  lea     rcx, [rsp+68h+arg_0]; IsMember
0x180001718  mov     [rsp+68h+arg_0], edi
0x18000171c  call    ?UserIsUACAdmin@@YAJPEAH@Z; UserIsUACAdmin(int *)
0x180001721  test    eax, eax
0x180001723  js      loc_180001816
0x180001729  cmp     [rsp+68h+arg_0], edi
0x18000172d  lea     rax, aConsentpromptb_0; "ConsentPromptBehaviorUser"
0x180001734  lea     r8, aConsentpromptb; "ConsentPromptBehaviorAdmin"
0x18000173b  mov     [rsp+68h+arg_18], edi
0x180001742  cmovz   r8, rax; lpValue
0x180001746  mov     [rsp+68h+arg_10], 4
0x180001751  lea     rax, [rsp+68h+arg_10]
0x180001759  mov     r9d, 10h; dwFlags
0x18000175f  mov     [rsp+68h+pcbData], rax; pcbData
0x180001764  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000176b  lea     rax, [rsp+68h+arg_18]
0x180001773  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000177a  mov     [rsp+68h+pvData], rax; pvData
0x18000177f  mov     [rsp+68h+pdwType], rdi; pdwType
0x180001784  call    cs:__imp_RegGetValueW
0x18000178b  nop     dword ptr [rax+rax+00h]
0x180001790  test    eax, eax
0x180001792  jg      loc_180001870
0x180001798  js      short loc_180001816
0x18000179a  lea     rax, [rsp+68h+var_28]
0x18000179f  mov     [rsp+68h+arg_10], edi
0x1800017a6  mov     [rsp+68h+pcbData], rax; pcbData
0x1800017ab  lea     r8, aPromptonsecure; "PromptOnSecureDesktop"
0x1800017b2  lea     rax, [rsp+68h+arg_10]
0x1800017ba  mov     [rsp+68h+var_28], 4
0x1800017c2  mov     [rsp+68h+pvData], rax; pvData
0x1800017c7  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800017ce  mov     r9d, 10h; dwFlags
0x1800017d4  mov     [rsp+68h+pdwType], rdi; pdwType
0x1800017d9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800017e0  call    cs:__imp_RegGetValueW
0x1800017e7  nop     dword ptr [rax+rax+00h]
0x1800017ec  test    eax, eax
0x1800017ee  jg      loc_18000187F
0x1800017f4  js      loc_18000188E
0x1800017fa  mov     ecx, [rsp+68h+arg_10]
0x180001801  mov     eax, [rsp+68h+arg_18]
0x180001808  test    eax, eax
0x18000180a  jz      short loc_180001827
0x18000180c  cmp     eax, 5
0x18000180f  jnz     short loc_18000182E
0x180001811  mov     ebx, 4
0x180001816  mov     eax, ebx
0x180001818  add     rsp, 58h
0x18000181c  pop     rdi
0x18000181d  pop     rbx
0x18000181e  retn
0x180001820  xor     al, al
0x180001822  jmp     loc_180001701
0x180001827  mov     ebx, 5
0x18000182c  jmp     short loc_180001816
0x18000182e  sub     eax, 1
0x180001831  jz      short loc_1800018B0
0x180001833  sub     eax, 1
0x180001836  jz      short loc_1800018A9
0x180001838  sub     eax, 1
0x18000183b  jz      short loc_180001895
0x18000183d  cmp     eax, 1
0x180001840  jnz     short loc_180001816
0x180001842  test    ecx, ecx
0x180001844  mov     ebx, 2
0x180001849  cmovnz  ebx, edi
0x18000184c  jmp     short loc_180001816
0x18000184e  movzx   eax, ax
0x180001851  or      eax, 80070000h
0x180001856  test    eax, eax
0x180001858  jmp     loc_1800016D2
0x18000185d  movzx   eax, al
0x180001860  lea     ebx, ds:6[rax*2]
0x180001867  jmp     short loc_180001816
0x180001869  mov     ebx, 7
0x18000186e  jmp     short loc_180001816
0x180001870  movzx   eax, ax
0x180001873  or      eax, 80070000h
0x180001878  test    eax, eax
0x18000187a  jmp     loc_180001798
0x18000187f  movzx   eax, ax
0x180001882  or      eax, 80070000h
0x180001887  test    eax, eax
0x180001889  jmp     loc_1800017F4
0x18000188e  mov     ecx, edi
0x180001890  jmp     loc_180001801
0x180001895  test    ecx, ecx
0x180001897  mov     ebx, 3
0x18000189c  mov     eax, 1
0x1800018a1  cmovnz  ebx, eax
0x1800018a4  jmp     loc_180001816
0x1800018a9  mov     ebx, edi
0x1800018ab  jmp     loc_180001816
0x1800018b0  mov     ebx, 1
0x1800018b5  jmp     loc_180001816
```
