# NfsSrv4PostOpenFileInstance

- ea: `0x18001ae1c`
- end: `0x18001b0b6`
- name: `NfsSrv4PostOpenFileInstance`
- size: `666`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x18001a53c`

## callees

- `0x18000990c`
- `0x18000be78`
- `0x18000eae4`
- `0x18000ec88`
- `0x18000efc8`
- `0x180014588`
- `0x180019250`
- `0x180019818`
- `0x180019940`
- `0x18001ae1c`
- `0x18001caec`
- `0x18001cc60`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x18001b02d`
- `ntdll!RtlStringFromGUID` at `0x18001b02d`
- `ntdll!RtlFreeUnicodeString` at `0x18001b069`
- `ntdll!RtlFreeUnicodeString` at `0x18001b069`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NfsSrv4PostOpenFileInstance(MI_Instance *self, __int64 a2, __int64 a3, __int64 a4)
{
  enum _MI_Result v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  GUID *p_Guid; // rax
  __int64 v19; // rdx
  PWSTR Buffer; // [rsp+30h] [rbp-D0h] BYREF
  GUID Guid; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v24; // [rsp+50h] [rbp-B0h]
  struct _UNICODE_STRING GuidString; // [rsp+60h] [rbp-A0h] BYREF
  MI_Instance selfa; // [rsp+80h] [rbp-80h] BYREF
  __int64 v27; // [rsp+E0h] [rbp-20h]
  char v28; // [rsp+E8h] [rbp-18h]
  int v29; // [rsp+100h] [rbp+0h]
  char v30; // [rsp+104h] [rbp+4h]
  int v31; // [rsp+108h] [rbp+8h]
  char v32; // [rsp+10Ch] [rbp+Ch]

  memset_0(&selfa, 0, 0xA0u);
  if ( self && self->ft )
  {
    v8 = ((unsigned int (__fastcall *)(MI_Instance *, void *, MI_Instance *))self->ft->IsA)(
           self,
           &MSFT_NfsOpenFile_rtti,
           &selfa);
    if ( v8 == MI_RESULT_OK )
    {
      v27 = *(_QWORD *)(a2 + 8);
      v28 = 1;
      if ( !*(_WORD *)(a2 + 64) )
        goto LABEL_14;
      v24 = 7;
      v23 = 0;
      LOWORD(Guid.Data1) = 0;
      if ( *(_WORD *)(a2 + 66) )
      {
        v9 = NfsMapVolumeDevicePathToMountPoint(
               (__int64)&GuidString,
               (unsigned __int16 *)(a2 + *(unsigned int *)(a2 + 68) + 80LL),
               a3,
               a4);
        std::wstring::operator=(&Guid, v9);
        LOBYTE(v10) = 1;
        std::wstring::_Tidy(&GuidString, v10, 0);
        v11 = std::char_traits<unsigned short>::length(a2 + 80);
        std::wstring::append(&Guid, v12, v11);
        while ( 1 )
        {
          v13 = std::char_traits<unsigned short>::length(L"\\\\");
          v15 = std::wstring::find(&Guid, L"\\\\", v14, v13);
          if ( v15 == -1 )
            break;
          std::wstring::replace(&Guid, v15);
        }
      }
      else
      {
        v16 = std::char_traits<unsigned short>::length(a2 + 80);
        std::wstring::assign(&Guid, v17, v16);
      }
      p_Guid = &Guid;
      if ( v24 >= 8 )
        p_Guid = *(GUID **)&Guid.Data1;
      Buffer = (PWSTR)p_Guid;
      v8 = ((unsigned int (__fastcall *)(MI_Instance *, __int64, PWSTR *))selfa.ft->SetElementAt)(&selfa, 3, &Buffer);
      LOBYTE(v19) = 1;
      std::wstring::_Tidy(&Guid, v19, 0);
      if ( v8 == MI_RESULT_OK )
      {
LABEL_14:
        v8 = NfsSetUserAccountNameOnInstance(&selfa, (PSID)(a2 + *(unsigned int *)(a2 + 76) + 80LL));
        if ( v8 == MI_RESULT_OK )
        {
          v29 = *(_DWORD *)(a2 + 56);
          v30 = 1;
          v31 = *(_DWORD *)(a2 + 60);
          v32 = 1;
          GuidString = *(struct _UNICODE_STRING *)(a2 + 36);
          v8 = (unsigned int)NfsSetNetworkNameOnInstance(&selfa, *(_BYTE *)(a2 + 32), (GUID *)&GuidString);
          if ( v8 == MI_RESULT_OK )
          {
            GuidString = 0;
            Guid = *(GUID *)(a2 + 16);
            if ( RtlStringFromGUID(&Guid, &GuidString) < 0 )
            {
              v8 = MI_RESULT_FAILED;
            }
            else
            {
              Buffer = GuidString.Buffer;
              v8 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, PWSTR *, _QWORD, _DWORD))selfa.ft->SetElementAt)(
                     &selfa,
                     0,
                     &Buffer,
                     (unsigned int)(v8 + 13),
                     0);
              RtlFreeUnicodeString(&GuidString);
              if ( v8 == MI_RESULT_OK )
                MI_Instance_Destruct(self);
            }
          }
        }
      }
      MI_Instance_Destruct(&selfa);
    }
  }
  else
  {
    return 4;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001ae1c  push    rbp
0x18001ae1e  push    rbx
0x18001ae1f  push    rsi
0x18001ae20  push    rdi
0x18001ae21  push    r12
0x18001ae23  push    r14
0x18001ae25  push    r15
0x18001ae27  lea     rbp, [rsp-30h]
0x18001ae2c  sub     rsp, 130h
0x18001ae33  mov     rax, cs:__security_cookie
0x18001ae3a  xor     rax, rsp
0x18001ae3d  mov     [rbp+60h+var_40], rax
0x18001ae41  mov     r15, r9
0x18001ae44  mov     r14, r8
0x18001ae47  mov     rdi, rdx
0x18001ae4a  mov     rsi, rcx
0x18001ae4d  xor     edx, edx; Val
0x18001ae4f  mov     r8d, 0A0h; Size
0x18001ae55  lea     rcx, [rbp+60h+self]; void *
0x18001ae59  call    memset_0
0x18001ae5e  xor     r12d, r12d
0x18001ae61  test    rsi, rsi
0x18001ae64  jz      loc_18001B091
0x18001ae6a  mov     rax, [rsi]
0x18001ae6d  test    rax, rax
0x18001ae70  jz      loc_18001B091
0x18001ae76  lea     r8, [rbp+60h+self]
0x18001ae7a  lea     rdx, MSFT_NfsOpenFile_rtti
0x18001ae81  mov     rcx, rsi
0x18001ae84  mov     rax, [rax+18h]
0x18001ae88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae8d  mov     ebx, eax
0x18001ae8f  test    eax, eax
0x18001ae91  jnz     loc_18001B096
0x18001ae97  mov     rax, [rdi+8]
0x18001ae9b  mov     [rbp+60h+var_80], rax
0x18001ae9f  mov     [rbp+60h+var_78], 1
0x18001aea3  cmp     [rdi+40h], r12w
0x18001aea8  jz      loc_18001AFBF
0x18001aeae  mov     [rsp+160h+var_110], 7
0x18001aeb7  mov     [rsp+160h+var_118], r12
0x18001aebc  mov     word ptr [rsp+160h+Guid.Data1], r12w
0x18001aec2  cmp     [rdi+42h], r12w
0x18001aec7  jz      loc_18001AF52
0x18001aecd  mov     edx, [rdi+44h]
0x18001aed0  add     rdx, 50h ; 'P'
0x18001aed4  add     rdx, rdi
0x18001aed7  mov     r9, r15
0x18001aeda  mov     r8, r14
0x18001aedd  lea     rcx, [rsp+160h+GuidString]
0x18001aee2  call    NfsMapVolumeDevicePathToMountPoint
0x18001aee7  mov     rdx, rax
0x18001aeea  lea     rcx, [rsp+160h+Guid]
0x18001aeef  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001aef4  xor     r8d, r8d
0x18001aef7  mov     dl, 1
0x18001aef9  lea     rcx, [rsp+160h+GuidString]
0x18001aefe  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001af03  lea     rcx, [rdi+50h]
0x18001af07  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001af0c  mov     r8, rax
0x18001af0f  mov     rdx, rcx
0x18001af12  lea     rcx, [rsp+160h+Guid]
0x18001af17  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18001af1c  lea     rbx, asc_180049D88; "\\\\"
0x18001af23  jmp     short loc_18001AF32
0x18001af25  mov     rdx, rax
0x18001af28  lea     rcx, [rsp+160h+Guid]
0x18001af2d  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0PEBG@Z; std::wstring::replace(unsigned __int64,unsigned __int64,ushort const *)
0x18001af32  mov     rcx, rbx
0x18001af35  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001af3a  mov     r9, rax
0x18001af3d  mov     rdx, rbx
0x18001af40  lea     rcx, [rsp+160h+Guid]
0x18001af45  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x18001af4a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001af4e  jnz     short loc_18001AF25
0x18001af50  jmp     short loc_18001AF6B
0x18001af52  lea     rcx, [rdi+50h]
0x18001af56  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001af5b  mov     r8, rax
0x18001af5e  mov     rdx, rcx
0x18001af61  lea     rcx, [rsp+160h+Guid]
0x18001af66  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001af6b  lea     rax, [rsp+160h+Guid]
0x18001af70  cmp     [rsp+160h+var_110], 8
0x18001af76  cmovnb  rax, qword ptr [rsp+160h+Guid.Data1]
0x18001af7c  mov     [rsp+160h+var_130], rax
0x18001af81  mov     rax, [rbp+60h+self.ft]
0x18001af85  mov     [rsp+160h+var_140], r12d
0x18001af8a  mov     r9d, 0Dh
0x18001af90  lea     r8, [rsp+160h+var_130]
0x18001af95  lea     edx, [r9-0Ah]
0x18001af99  lea     rcx, [rbp+60h+self]
0x18001af9d  mov     rax, [rax+50h]
0x18001afa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afa6  mov     ebx, eax
0x18001afa8  xor     r8d, r8d
0x18001afab  mov     dl, 1
0x18001afad  lea     rcx, [rsp+160h+Guid]
0x18001afb2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001afb7  test    ebx, ebx
0x18001afb9  jnz     loc_18001B086
0x18001afbf  mov     edx, [rdi+4Ch]
0x18001afc2  add     rdx, 50h ; 'P'
0x18001afc6  add     rdx, rdi; Sid
0x18001afc9  lea     rcx, [rbp+60h+self]; self
0x18001afcd  call    ?NfsSetUserAccountNameOnInstance@@YA?AW4_MI_Result@@PEAU_MI_Instance@@PEAX@Z; NfsSetUserAccountNameOnInstance(_MI_Instance *,void *)
0x18001afd2  mov     ebx, eax
0x18001afd4  test    eax, eax
0x18001afd6  jnz     loc_18001B086
0x18001afdc  mov     eax, [rdi+38h]
0x18001afdf  mov     [rbp+60h+var_60], eax
0x18001afe2  mov     [rbp+60h+var_5C], 1
0x18001afe6  mov     eax, [rdi+3Ch]
0x18001afe9  mov     [rbp+60h+var_58], eax
0x18001afec  mov     [rbp+60h+var_54], 1
0x18001aff0  movups  xmm0, xmmword ptr [rdi+24h]
0x18001aff4  movdqu  xmmword ptr [rsp+160h+GuidString.Length], xmm0
0x18001affa  lea     r8, [rsp+160h+GuidString]
0x18001afff  mov     dl, [rdi+20h]
0x18001b002  lea     rcx, [rbp+60h+self]; self
0x18001b006  call    NfsSetNetworkNameOnInstance
0x18001b00b  mov     ebx, eax
0x18001b00d  test    eax, eax
0x18001b00f  jnz     short loc_18001B086
0x18001b011  xorps   xmm0, xmm0
0x18001b014  movups  xmmword ptr [rsp+160h+GuidString.Length], xmm0
0x18001b019  movups  xmm1, xmmword ptr [rdi+10h]
0x18001b01d  movdqu  xmmword ptr [rsp+160h+Guid.Data1], xmm1
0x18001b023  lea     rdx, [rsp+160h+GuidString]; GuidString
0x18001b028  lea     rcx, [rsp+160h+Guid]; Guid
0x18001b02d  call    cs:__imp_RtlStringFromGUID
0x18001b033  test    eax, eax
0x18001b035  js      short loc_18001B081
0x18001b037  mov     rax, [rsp+160h+GuidString.Buffer]
0x18001b03c  mov     [rsp+160h+var_130], rax
0x18001b041  mov     rax, [rbp+60h+self.ft]
0x18001b045  mov     [rsp+160h+var_140], r12d
0x18001b04a  lea     r9d, [rbx+0Dh]
0x18001b04e  lea     r8, [rsp+160h+var_130]
0x18001b053  xor     edx, edx
0x18001b055  lea     rcx, [rbp+60h+self]
0x18001b059  mov     rax, [rax+50h]
0x18001b05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b062  mov     ebx, eax
0x18001b064  lea     rcx, [rsp+160h+GuidString]; UnicodeString
0x18001b069  call    cs:__imp_RtlFreeUnicodeString
0x18001b06f  test    ebx, ebx
0x18001b071  jnz     short loc_18001B086
0x18001b073  lea     rdx, [rbp+60h+self]
0x18001b077  mov     rcx, rsi; self
0x18001b07a  call    MI_Instance_Destruct
0x18001b07f  jmp     short loc_18001B086
0x18001b081  mov     ebx, 1
0x18001b086  lea     rcx, [rbp+60h+self]; self
0x18001b08a  call    MI_Instance_Destruct
0x18001b08f  jmp     short loc_18001B096
0x18001b091  mov     ebx, 4
0x18001b096  mov     eax, ebx
0x18001b098  mov     rcx, [rbp+60h+var_40]
0x18001b09c  xor     rcx, rsp; StackCookie
0x18001b09f  call    __security_check_cookie
0x18001b0a4  add     rsp, 130h
0x18001b0ab  pop     r15
0x18001b0ad  pop     r14
0x18001b0af  pop     r12
0x18001b0b1  pop     rdi
0x18001b0b2  pop     rsi
0x18001b0b3  pop     rbx
0x18001b0b4  pop     rbp
0x18001b0b5  retn
```
