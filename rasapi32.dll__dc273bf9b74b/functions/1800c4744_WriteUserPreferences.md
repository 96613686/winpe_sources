# WriteUserPreferences

- ea: `0x1800c4744`
- end: `0x1800c4d1b`
- name: `WriteUserPreferences`
- size: `1495`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c3744`

## callees

- `0x1800c42ec`
- `0x1800c4504`
- `0x1800c4744`
- `0x1800c52f0`
- `0x1800c5414`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c4cda`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c4cda`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c47a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c47d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c480d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4841`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4875`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c48a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c48dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4911`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4945`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4979`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c49ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c49e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4a15`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4a49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4a7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4ab1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4ae5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4b19`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4b50`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4b87`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4bbe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c47a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c47d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c480d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4841`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4875`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c48a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c48dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4911`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4945`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4979`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c49ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c49e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4a15`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4a49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4a7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4ab1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4ae5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4b19`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4b50`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4b87`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4bbe`
- `rtutils!TracePrintfExA` at `0x1800c4776`
- `rtutils!TracePrintfExA` at `0x1800c4d00`
- `rtutils!TracePrintfExA` at `0x1800c4776`
- `rtutils!TracePrintfExA` at `0x1800c4d00`

## string_xrefs

- `0x1800c498c`: `RedialAttempts`
- `0x1800c4958`: `SkipConnectComplete`
- `0x1800c4a28`: `RedialOnLinkFailure`
- `0x1800c4c9f`: `AlternatePhonebookPath`
- `0x1800c4cd0`: `PersonalPhonebookPath`
- `0x1800c476a`: `WriteUserPreferences`
- `0x1800c4cf4`: `WriteUserPreferences=%d`

## pseudocode

```c
__int64 __fastcall WriteUserPreferences(HKEY hKey, int *a2)
{
  unsigned int v4; // ebx
  int Data; // [rsp+58h] [rbp+28h] BYREF

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "WriteUserPreferences");
  Data = *a2;
  v4 = RegSetValueExW(hKey, L"OperatorDial", 0, 4u, (const BYTE *)&Data, 4u);
  if ( !v4 )
  {
    Data = a2[1];
    v4 = RegSetValueExW(hKey, L"PreviewPhoneNumber", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v4 )
    {
      Data = a2[2];
      v4 = RegSetValueExW(hKey, L"UseLocation", 0, 4u, (const BYTE *)&Data, 4u);
      if ( !v4 )
      {
        Data = a2[3];
        v4 = RegSetValueExW(hKey, L"ShowLights", 0, 4u, (const BYTE *)&Data, 4u);
        if ( !v4 )
        {
          Data = a2[4];
          v4 = RegSetValueExW(hKey, L"ShowConnectStatus", 0, 4u, (const BYTE *)&Data, 4u);
          if ( !v4 )
          {
            Data = a2[9];
            v4 = RegSetValueExW(hKey, L"NewEntryWizard", 0, 4u, (const BYTE *)&Data, 4u);
            if ( !v4 )
            {
              Data = a2[5];
              v4 = RegSetValueExW(hKey, L"CloseOnDial", 0, 4u, (const BYTE *)&Data, 4u);
              if ( !v4 )
              {
                Data = a2[6];
                v4 = RegSetValueExW(hKey, L"AllowLogonPhonebookEdits", 0, 4u, (const BYTE *)&Data, 4u);
                if ( !v4 )
                {
                  Data = a2[7];
                  v4 = RegSetValueExW(hKey, L"AllowLogonLocationEdits", 0, 4u, (const BYTE *)&Data, 4u);
                  if ( !v4 )
                  {
                    Data = a2[8];
                    v4 = RegSetValueExW(hKey, L"SkipConnectComplete", 0, 4u, (const BYTE *)&Data, 4u);
                    if ( !v4 )
                    {
                      Data = a2[10];
                      v4 = RegSetValueExW(hKey, L"RedialAttempts", 0, 4u, (const BYTE *)&Data, 4u);
                      if ( !v4 )
                      {
                        Data = a2[11];
                        v4 = RegSetValueExW(hKey, L"RedialSeconds", 0, 4u, (const BYTE *)&Data, 4u);
                        if ( !v4 )
                        {
                          Data = a2[12];
                          v4 = RegSetValueExW(hKey, L"IdleHangUpSeconds", 0, 4u, (const BYTE *)&Data, 4u);
                          if ( !v4 )
                          {
                            Data = a2[13];
                            v4 = RegSetValueExW(hKey, L"RedialOnLinkFailure", 0, 4u, (const BYTE *)&Data, 4u);
                            if ( !v4 )
                            {
                              Data = a2[14];
                              v4 = RegSetValueExW(hKey, L"PopupOnTopWhenRedialing", 0, 4u, (const BYTE *)&Data, 4u);
                              if ( !v4 )
                              {
                                Data = a2[15];
                                v4 = RegSetValueExW(hKey, L"ExpandAutoDialQuery", 0, 4u, (const BYTE *)&Data, 4u);
                                if ( !v4 )
                                {
                                  Data = a2[16];
                                  v4 = RegSetValueExW(hKey, L"CallbackMode", 0, 4u, (const BYTE *)&Data, 4u);
                                  if ( !v4 )
                                  {
                                    Data = a2[22];
                                    v4 = RegSetValueExW(hKey, L"PhonebookMode", 0, 4u, (const BYTE *)&Data, 4u);
                                    if ( !v4 )
                                    {
                                      Data = a2[32];
                                      v4 = RegSetValueExW(hKey, L"UseAreaAndCountry", 0, 4u, (const BYTE *)&Data, 4u);
                                      if ( !v4 )
                                      {
                                        Data = a2[40];
                                        v4 = RegSetValueExW(hKey, L"WindowX", 0, 4u, (const BYTE *)&Data, 4u);
                                        if ( !v4 )
                                        {
                                          Data = a2[41];
                                          RegSetValueExW(hKey, L"WindowY", 0, 4u, (const BYTE *)&Data, 4u);
                                          v4 = SetCallbackList(hKey, *((_QWORD *)a2 + 9));
                                          if ( !v4 )
                                          {
                                            v4 = SetRegMultiSz(hKey, L"Phonebooks");
                                            if ( !v4 )
                                            {
                                              v4 = SetRegMultiSz(hKey, L"AreaCodes");
                                              if ( !v4 )
                                              {
                                                v4 = SetRegMultiSz(hKey, L"Prefixes");
                                                if ( !v4 )
                                                {
                                                  v4 = SetRegMultiSz(hKey, L"Suffixes");
                                                  if ( !v4 )
                                                  {
                                                    v4 = SetLocationList(hKey, *((_QWORD *)a2 + 19));
                                                    if ( !v4 )
                                                    {
                                                      v4 = SetRegSz(hKey, L"LastCallbackByCaller");
                                                      if ( !v4 )
                                                      {
                                                        v4 = SetRegSz(hKey, L"PersonalPhonebookFile");
                                                        if ( !v4 )
                                                        {
                                                          v4 = SetRegSz(hKey, L"AlternatePhonebookPath");
                                                          if ( !v4 )
                                                          {
                                                            v4 = SetRegSz(hKey, L"DefaultEntry");
                                                            if ( !v4 )
                                                            {
                                                              RegDeleteValueW(hKey, L"PersonalPhonebookPath");
                                                              a2[45] = 0;
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "WriteUserPreferences=%d", v4);
  return v4;
}

```

## disassembly

```asm
0x1800c4744  mov     [rsp-18h+arg_0], rbx
0x1800c4749  mov     [rsp-18h+arg_10], rsi
0x1800c474e  push    rbp
0x1800c474f  push    rdi
0x1800c4750  push    r14
0x1800c4752  mov     rbp, rsp
0x1800c4755  sub     rsp, 30h
0x1800c4759  mov     rsi, rcx
0x1800c475c  mov     rdi, rdx
0x1800c475f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c4765  cmp     ecx, 0FFFFFFFFh
0x1800c4768  jz      short loc_1800C477C
0x1800c476a  lea     r8, aWriteuserprefe; "WriteUserPreferences"
0x1800c4771  mov     edx, 0Ch; dwFlags
0x1800c4776  call    cs:__imp_TracePrintfExA
0x1800c477c  mov     eax, [rdi]
0x1800c477e  lea     rdx, aOperatordial; "OperatorDial"
0x1800c4785  mov     [rbp+Data], eax
0x1800c4788  mov     r14d, 4
0x1800c478e  lea     rax, [rbp+Data]
0x1800c4792  mov     [rsp+30h+cbData], r14d; cbData
0x1800c4797  mov     r9d, r14d; dwType
0x1800c479a  mov     [rsp+30h+lpData], rax; lpData
0x1800c479f  xor     r8d, r8d; Reserved
0x1800c47a2  mov     rcx, rsi; hKey
0x1800c47a5  call    cs:__imp_RegSetValueExW
0x1800c47ab  mov     ebx, eax
0x1800c47ad  test    eax, eax
0x1800c47af  jnz     loc_1800C4CE6
0x1800c47b5  mov     eax, [rdi+4]
0x1800c47b8  lea     rdx, aPreviewphonenu; "PreviewPhoneNumber"
0x1800c47bf  mov     [rbp+Data], eax
0x1800c47c2  mov     r9d, r14d; dwType
0x1800c47c5  lea     rax, [rbp+Data]
0x1800c47c9  mov     [rsp+30h+cbData], r14d; cbData
0x1800c47ce  xor     r8d, r8d; Reserved
0x1800c47d1  mov     [rsp+30h+lpData], rax; lpData
0x1800c47d6  mov     rcx, rsi; hKey
0x1800c47d9  call    cs:__imp_RegSetValueExW
0x1800c47df  mov     ebx, eax
0x1800c47e1  test    eax, eax
0x1800c47e3  jnz     loc_1800C4CE6
0x1800c47e9  mov     eax, [rdi+8]
0x1800c47ec  lea     rdx, aUselocation; "UseLocation"
0x1800c47f3  mov     [rbp+Data], eax
0x1800c47f6  mov     r9d, r14d; dwType
0x1800c47f9  lea     rax, [rbp+Data]
0x1800c47fd  mov     [rsp+30h+cbData], r14d; cbData
0x1800c4802  xor     r8d, r8d; Reserved
0x1800c4805  mov     [rsp+30h+lpData], rax; lpData
0x1800c480a  mov     rcx, rsi; hKey
0x1800c480d  call    cs:__imp_RegSetValueExW
0x1800c4813  mov     ebx, eax
0x1800c4815  test    eax, eax
0x1800c4817  jnz     loc_1800C4CE6
0x1800c481d  mov     eax, [rdi+0Ch]
0x1800c4820  lea     rdx, aShowlights; "ShowLights"
0x1800c4827  mov     [rbp+Data], eax
0x1800c482a  mov     r9d, r14d; dwType
0x1800c482d  lea     rax, [rbp+Data]
0x1800c4831  mov     [rsp+30h+cbData], r14d; cbData
0x1800c4836  xor     r8d, r8d; Reserved
0x1800c4839  mov     [rsp+30h+lpData], rax; lpData
0x1800c483e  mov     rcx, rsi; hKey
0x1800c4841  call    cs:__imp_RegSetValueExW
0x1800c4847  mov     ebx, eax
0x1800c4849  test    eax, eax
0x1800c484b  jnz     loc_1800C4CE6
0x1800c4851  mov     eax, [rdi+10h]
0x1800c4854  lea     rdx, aShowconnectsta; "ShowConnectStatus"
0x1800c485b  mov     [rbp+Data], eax
0x1800c485e  mov     r9d, r14d; dwType
0x1800c4861  lea     rax, [rbp+Data]
0x1800c4865  mov     [rsp+30h+cbData], r14d; cbData
0x1800c486a  xor     r8d, r8d; Reserved
0x1800c486d  mov     [rsp+30h+lpData], rax; lpData
0x1800c4872  mov     rcx, rsi; hKey
0x1800c4875  call    cs:__imp_RegSetValueExW
0x1800c487b  mov     ebx, eax
0x1800c487d  test    eax, eax
0x1800c487f  jnz     loc_1800C4CE6
0x1800c4885  mov     eax, [rdi+24h]
0x1800c4888  lea     rdx, aNewentrywizard; "NewEntryWizard"
0x1800c488f  mov     [rbp+Data], eax
0x1800c4892  mov     r9d, r14d; dwType
0x1800c4895  lea     rax, [rbp+Data]
0x1800c4899  mov     [rsp+30h+cbData], r14d; cbData
0x1800c489e  xor     r8d, r8d; Reserved
0x1800c48a1  mov     [rsp+30h+lpData], rax; lpData
0x1800c48a6  mov     rcx, rsi; hKey
0x1800c48a9  call    cs:__imp_RegSetValueExW
0x1800c48af  mov     ebx, eax
0x1800c48b1  test    eax, eax
0x1800c48b3  jnz     loc_1800C4CE6
0x1800c48b9  mov     eax, [rdi+14h]
0x1800c48bc  lea     rdx, aCloseondial; "CloseOnDial"
0x1800c48c3  mov     [rbp+Data], eax
0x1800c48c6  mov     r9d, r14d; dwType
0x1800c48c9  lea     rax, [rbp+Data]
0x1800c48cd  mov     [rsp+30h+cbData], r14d; cbData
0x1800c48d2  xor     r8d, r8d; Reserved
0x1800c48d5  mov     [rsp+30h+lpData], rax; lpData
0x1800c48da  mov     rcx, rsi; hKey
0x1800c48dd  call    cs:__imp_RegSetValueExW
0x1800c48e3  mov     ebx, eax
0x1800c48e5  test    eax, eax
0x1800c48e7  jnz     loc_1800C4CE6
0x1800c48ed  mov     eax, [rdi+18h]
0x1800c48f0  lea     rdx, aAllowlogonphon; "AllowLogonPhonebookEdits"
0x1800c48f7  mov     [rbp+Data], eax
0x1800c48fa  mov     r9d, r14d; dwType
0x1800c48fd  lea     rax, [rbp+Data]
0x1800c4901  mov     [rsp+30h+cbData], r14d; cbData
0x1800c4906  xor     r8d, r8d; Reserved
0x1800c4909  mov     [rsp+30h+lpData], rax; lpData
0x1800c490e  mov     rcx, rsi; hKey
0x1800c4911  call    cs:__imp_RegSetValueExW
0x1800c4917  mov     ebx, eax
0x1800c4919  test    eax, eax
0x1800c491b  jnz     loc_1800C4CE6
0x1800c4921  mov     eax, [rdi+1Ch]
0x1800c4924  lea     rdx, aAllowlogonloca; "AllowLogonLocationEdits"
0x1800c492b  mov     [rbp+Data], eax
0x1800c492e  mov     r9d, r14d; dwType
0x1800c4931  lea     rax, [rbp+Data]
0x1800c4935  mov     [rsp+30h+cbData], r14d; cbData
0x1800c493a  xor     r8d, r8d; Reserved
0x1800c493d  mov     [rsp+30h+lpData], rax; lpData
0x1800c4942  mov     rcx, rsi; hKey
0x1800c4945  call    cs:__imp_RegSetValueExW
0x1800c494b  mov     ebx, eax
0x1800c494d  test    eax, eax
0x1800c494f  jnz     loc_1800C4CE6
0x1800c4955  mov     eax, [rdi+20h]
0x1800c4958  lea     rdx, aSkipconnectcom; "SkipConnectComplete"
0x1800c495f  mov     [rbp+Data], eax
0x1800c4962  mov     r9d, r14d; dwType
0x1800c4965  lea     rax, [rbp+Data]
0x1800c4969  mov     [rsp+30h+cbData], r14d; cbData
0x1800c496e  xor     r8d, r8d; Reserved
0x1800c4971  mov     [rsp+30h+lpData], rax; lpData
0x1800c4976  mov     rcx, rsi; hKey
0x1800c4979  call    cs:__imp_RegSetValueExW
0x1800c497f  mov     ebx, eax
0x1800c4981  test    eax, eax
0x1800c4983  jnz     loc_1800C4CE6
0x1800c4989  mov     eax, [rdi+28h]
0x1800c498c  lea     rdx, aRedialattempts_0; "RedialAttempts"
0x1800c4993  mov     [rbp+Data], eax
0x1800c4996  mov     r9d, r14d; dwType
0x1800c4999  lea     rax, [rbp+Data]
0x1800c499d  mov     [rsp+30h+cbData], r14d; cbData
0x1800c49a2  xor     r8d, r8d; Reserved
0x1800c49a5  mov     [rsp+30h+lpData], rax; lpData
0x1800c49aa  mov     rcx, rsi; hKey
0x1800c49ad  call    cs:__imp_RegSetValueExW
0x1800c49b3  mov     ebx, eax
0x1800c49b5  test    eax, eax
0x1800c49b7  jnz     loc_1800C4CE6
0x1800c49bd  mov     eax, [rdi+2Ch]
0x1800c49c0  lea     rdx, aRedialseconds; "RedialSeconds"
0x1800c49c7  mov     [rbp+Data], eax
0x1800c49ca  mov     r9d, r14d; dwType
0x1800c49cd  lea     rax, [rbp+Data]
0x1800c49d1  mov     [rsp+30h+cbData], r14d; cbData
0x1800c49d6  xor     r8d, r8d; Reserved
0x1800c49d9  mov     [rsp+30h+lpData], rax; lpData
0x1800c49de  mov     rcx, rsi; hKey
0x1800c49e1  call    cs:__imp_RegSetValueExW
0x1800c49e7  mov     ebx, eax
0x1800c49e9  test    eax, eax
0x1800c49eb  jnz     loc_1800C4CE6
0x1800c49f1  mov     eax, [rdi+30h]
0x1800c49f4  lea     rdx, aIdlehangupseco; "IdleHangUpSeconds"
0x1800c49fb  mov     [rbp+Data], eax
0x1800c49fe  mov     r9d, r14d; dwType
0x1800c4a01  lea     rax, [rbp+Data]
0x1800c4a05  mov     [rsp+30h+cbData], r14d; cbData
0x1800c4a0a  xor     r8d, r8d; Reserved
0x1800c4a0d  mov     [rsp+30h+lpData], rax; lpData
0x1800c4a12  mov     rcx, rsi; hKey
0x1800c4a15  call    cs:__imp_RegSetValueExW
0x1800c4a1b  mov     ebx, eax
0x1800c4a1d  test    eax, eax
0x1800c4a1f  jnz     loc_1800C4CE6
0x1800c4a25  mov     eax, [rdi+34h]
0x1800c4a28  lea     rdx, aRedialonlinkfa; "RedialOnLinkFailure"
0x1800c4a2f  mov     [rbp+Data], eax
0x1800c4a32  mov     r9d, r14d; dwType
0x1800c4a35  lea     rax, [rbp+Data]
0x1800c4a39  mov     [rsp+30h+cbData], r14d; cbData
0x1800c4a3e  xor     r8d, r8d; Reserved
0x1800c4a41  mov     [rsp+30h+lpData], rax; lpData
0x1800c4a46  mov     rcx, rsi; hKey
0x1800c4a49  call    cs:__imp_RegSetValueExW
0x1800c4a4f  mov     ebx, eax
0x1800c4a51  test    eax, eax
0x1800c4a53  jnz     loc_1800C4CE6
0x1800c4a59  mov     eax, [rdi+38h]
0x1800c4a5c  lea     rdx, aPopupontopwhen; "PopupOnTopWhenRedialing"
0x1800c4a63  mov     [rbp+Data], eax
0x1800c4a66  mov     r9d, r14d; dwType
0x1800c4a69  lea     rax, [rbp+Data]
0x1800c4a6d  mov     [rsp+30h+cbData], r14d; cbData
0x1800c4a72  xor     r8d, r8d; Reserved
0x1800c4a75  mov     [rsp+30h+lpData], rax; lpData
0x1800c4a7a  mov     rcx, rsi; hKey
0x1800c4a7d  call    cs:__imp_RegSetValueExW
0x1800c4a83  mov     ebx, eax
0x1800c4a85  test    eax, eax
0x1800c4a87  jnz     loc_1800C4CE6
0x1800c4a8d  mov     eax, [rdi+3Ch]
0x1800c4a90  lea     rdx, aExpandautodial; "ExpandAutoDialQuery"
0x1800c4a97  mov     [rbp+Data], eax
0x1800c4a9a  mov     r9d, r14d; dwType
0x1800c4a9d  lea     rax, [rbp+Data]
0x1800c4aa1  mov     [rsp+30h+cbData], r14d; cbData
0x1800c4aa6  xor     r8d, r8d; Reserved
0x1800c4aa9  mov     [rsp+30h+lpData], rax; lpData
0x1800c4aae  mov     rcx, rsi; hKey
0x1800c4ab1  call    cs:__imp_RegSetValueExW
0x1800c4ab7  mov     ebx, eax
0x1800c4ab9  test    eax, eax
0x1800c4abb  jnz     loc_1800C4CE6
0x1800c4ac1  mov     eax, [rdi+40h]
0x1800c4ac4  lea     rdx, aCallbackmode_0; "CallbackMode"
0x1800c4acb  mov     [rbp+Data], eax
0x1800c4ace  mov     r9d, r14d; dwType
0x1800c4ad1  lea     rax, [rbp+Data]
0x1800c4ad5  mov     [rsp+30h+cbData], r14d; cbData
0x1800c4ada  xor     r8d, r8d; Reserved
0x1800c4add  mov     [rsp+30h+lpData], rax; lpData
0x1800c4ae2  mov     rcx, rsi; hKey
0x1800c4ae5  call    cs:__imp_RegSetValueExW
0x1800c4aeb  mov     ebx, eax
0x1800c4aed  test    eax, eax
0x1800c4aef  jnz     loc_1800C4CE6
0x1800c4af5  mov     eax, [rdi+58h]
0x1800c4af8  lea     rdx, aPhonebookmode; "PhonebookMode"
0x1800c4aff  mov     [rbp+Data], eax
0x1800c4b02  mov     r9d, r14d; dwType
0x1800c4b05  lea     rax, [rbp+Data]
0x1800c4b09  mov     [rsp+30h+cbData], r14d; cbData
0x1800c4b0e  xor     r8d, r8d; Reserved
0x1800c4b11  mov     [rsp+30h+lpData], rax; lpData
0x1800c4b16  mov     rcx, rsi; hKey
0x1800c4b19  call    cs:__imp_RegSetValueExW
0x1800c4b1f  mov     ebx, eax
0x1800c4b21  test    eax, eax
0x1800c4b23  jnz     loc_1800C4CE6
0x1800c4b29  mov     eax, [rdi+80h]
0x1800c4b2f  lea     rdx, aUseareaandcoun; "UseAreaAndCountry"
0x1800c4b36  mov     [rbp+Data], eax
0x1800c4b39  mov     r9d, r14d; dwType
0x1800c4b3c  lea     rax, [rbp+Data]
0x1800c4b40  mov     [rsp+30h+cbData], r14d; cbData
0x1800c4b45  xor     r8d, r8d; Reserved
0x1800c4b48  mov     [rsp+30h+lpData], rax; lpData
0x1800c4b4d  mov     rcx, rsi; hKey
0x1800c4b50  call    cs:__imp_RegSetValueExW
0x1800c4b56  mov     ebx, eax
0x1800c4b58  test    eax, eax
0x1800c4b5a  jnz     loc_1800C4CE6
0x1800c4b60  mov     eax, [rdi+0A0h]
0x1800c4b66  lea     rdx, aWindowx; "WindowX"
0x1800c4b6d  mov     [rbp+Data], eax
0x1800c4b70  mov     r9d, r14d; dwType
0x1800c4b73  lea     rax, [rbp+Data]
0x1800c4b77  mov     [rsp+30h+cbData], r14d; cbData
0x1800c4b7c  xor     r8d, r8d; Reserved
0x1800c4b7f  mov     [rsp+30h+lpData], rax; lpData
0x1800c4b84  mov     rcx, rsi; hKey
0x1800c4b87  call    cs:__imp_RegSetValueExW
0x1800c4b8d  mov     ebx, eax
0x1800c4b8f  test    eax, eax
0x1800c4b91  jnz     loc_1800C4CE6
0x1800c4b97  mov     eax, [rdi+0A4h]
0x1800c4b9d  lea     rdx, aWindowy; "WindowY"
0x1800c4ba4  mov     [rbp+Data], eax
0x1800c4ba7  mov     r9d, r14d; dwType
0x1800c4baa  lea     rax, [rbp+Data]
0x1800c4bae  mov     [rsp+30h+cbData], r14d; cbData
0x1800c4bb3  xor     r8d, r8d; Reserved
0x1800c4bb6  mov     [rsp+30h+lpData], rax; lpData
0x1800c4bbb  mov     rcx, rsi; hKey
0x1800c4bbe  call    cs:__imp_RegSetValueExW
0x1800c4bc4  mov     rdx, [rdi+48h]
0x1800c4bc8  mov     rcx, rsi
0x1800c4bcb  call    SetCallbackList
0x1800c4bd0  mov     ebx, eax
0x1800c4bd2  test    eax, eax
0x1800c4bd4  jnz     loc_1800C4CE6
0x1800c4bda  mov     r8, [rdi+70h]
0x1800c4bde  lea     rdx, aPhonebooks; "Phonebooks"
0x1800c4be5  mov     rcx, rsi; hKey
0x1800c4be8  call    SetRegMultiSz
0x1800c4bed  mov     ebx, eax
0x1800c4bef  test    eax, eax
0x1800c4bf1  jnz     loc_1800C4CE6
0x1800c4bf7  mov     r8, [rdi+78h]
  ... truncated ...
```
