# QuicConfigurationParamSet

- ea: `0x140041588`
- end: `0x1400417d7`
- name: `QuicConfigurationParamSet`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140001b00`

## callees

- `0x140005f0c`
- `0x14002bfd8`
- `0x14002cb4c`
- `0x14002d09c`
- `0x140035648`
- `0x14003695c`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14003ead8`
- `0x140041588`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14004167b`
- `ntoskrnl!_snprintf_s` at `0x14004175a`
- `ntoskrnl!_snprintf_s` at `0x14004167b`
- `ntoskrnl!_snprintf_s` at `0x14004175a`

## pseudocode

```c
__int64 __fastcall QuicConfigurationParamSet(__int64 a1, int a2, unsigned int a3, _BYTE *a4)
{
  __int64 result; // rax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  struct _SecHandle *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  char v17[144]; // [rsp+30h] [rbp-138h] BYREF
  char DstBuf[128]; // [rsp+C0h] [rbp-A8h] BYREF

  memset(v17, 0, sizeof(v17));
  if ( a2 != 50331648 )
  {
    switch ( a2 )
    {
      case 50331649:
        if ( a4 && a3 >= 0x51 )
        {
          v13 = *(struct _SecHandle **)(a1 + 48);
          if ( v13 )
            return CxPlatTlsSecConfigSetTicketKeys(v13);
          else
            return 3221225860LL;
        }
        break;
      case 50331650:
        v9 = 0;
        if ( a4 )
        {
          if ( (byte_14005C48E & 0x40) != 0 )
          {
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[cnfg][%p] Setting new settings", (const void *)a1);
            McTemplateU0s_EtwWriteTransfer(v10, (const EVENT_DESCRIPTOR *)QuicLogInfo, DstBuf);
          }
          result = QuicSettingsVersionSettingsToInternal(a3, a4, v17);
          if ( (int)result >= 0 )
          {
            LOBYTE(v12) = 1;
            LOBYTE(v11) = 1;
            if ( !(unsigned __int8)QuicSettingApply(a1 + 96, v11, v12, v17) )
              v9 = -1073741811;
            QuicSettingsCleanup(v17);
            return v9;
          }
          return result;
        }
        break;
      case 50331651:
        return CxPlatSecConfigParamSet(*(_QWORD *)(a1 + 48), 50331651, a3, a4);
      default:
        if ( a2 == -2097151999 && a4 && a3 )
        {
          *(_QWORD *)(a1 + 96) |= 0x80000000uLL;
          *(_BYTE *)(a1 + 235) ^= (*(_BYTE *)(a1 + 235) ^ (*a4 << 6)) & 0x40;
          return 0;
        }
        return 3221225485LL;
    }
    return 3221225485LL;
  }
  if ( !a4 )
    return 3221225485LL;
  if ( (byte_14005C48E & 0x40) != 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[cnfg][%p] Setting new settings", (const void *)a1);
    McTemplateU0s_EtwWriteTransfer(v14, (const EVENT_DESCRIPTOR *)QuicLogInfo, DstBuf);
  }
  result = QuicSettingsSettingsToInternal(a3, a4, v17);
  if ( (int)result >= 0 )
  {
    LOBYTE(v16) = 1;
    LOBYTE(v15) = 1;
    return (unsigned __int8)QuicSettingApply(a1 + 96, v15, v16, v17) == 0 ? 0xC000000D : 0;
  }
  return result;
}

```

## disassembly

```asm
0x140041588  mov     [rsp+arg_8], rbx
0x14004158d  push    rbp
0x14004158e  push    rsi
0x14004158f  push    rdi
0x140041590  sub     rsp, 150h
0x140041597  mov     rax, cs:__security_cookie
0x14004159e  xor     rax, rsp
0x1400415a1  mov     [rsp+168h+var_28], rax
0x1400415a9  mov     ebp, r8d
0x1400415ac  mov     ebx, edx
0x1400415ae  mov     rsi, rcx
0x1400415b1  xor     edx, edx; Val
0x1400415b3  mov     r8d, 90h; Size
0x1400415b9  lea     rcx, [rsp+168h+var_138]; void *
0x1400415be  mov     rdi, r9
0x1400415c1  call    memset
0x1400415c6  cmp     ebx, 3000000h
0x1400415cc  jz      loc_14004172F
0x1400415d2  cmp     ebx, 3000001h
0x1400415d8  jz      loc_1400416E0
0x1400415de  cmp     ebx, 3000002h
0x1400415e4  jz      short loc_14004164A
0x1400415e6  cmp     ebx, 3000003h
0x1400415ec  jz      short loc_140041634
0x1400415ee  cmp     ebx, 83000001h
0x1400415f4  jnz     loc_1400417AE
0x1400415fa  test    rdi, rdi
0x1400415fd  jz      loc_1400417AE
0x140041603  cmp     ebp, 1
0x140041606  jb      loc_1400417AE
0x14004160c  mov     eax, 80000000h
0x140041611  or      [rsi+60h], rax
0x140041615  mov     al, [rsi+0EBh]
0x14004161b  mov     cl, [rdi]
0x14004161d  shl     cl, 6
0x140041620  xor     cl, al
0x140041622  and     cl, 40h
0x140041625  xor     cl, al
0x140041627  mov     [rsi+0EBh], cl
0x14004162d  xor     eax, eax
0x14004162f  jmp     loc_1400417B3
0x140041634  mov     rcx, [rsi+30h]
0x140041638  mov     r9, rdi
0x14004163b  mov     r8d, ebp
0x14004163e  mov     edx, ebx
0x140041640  call    CxPlatSecConfigParamSet
0x140041645  jmp     loc_1400417B3
0x14004164a  xor     ebx, ebx
0x14004164c  test    rdi, rdi
0x14004164f  jz      loc_1400417AE
0x140041655  test    cs:byte_14005C48E, 40h
0x14004165c  jz      short loc_14004169B
0x14004165e  lea     r9, aCnfgPSettingNe; "[cnfg][%p] Setting new settings"
0x140041665  mov     [rsp+168h+var_148], rsi
0x14004166a  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14004166e  lea     rcx, [rsp+168h+DstBuf]; DstBuf
0x140041676  mov     edx, 80h; SizeInBytes
0x14004167b  call    cs:__imp__snprintf_s
0x140041682  nop     dword ptr [rax+rax+00h]
0x140041687  lea     r8, [rsp+168h+DstBuf]
0x14004168f  lea     rdx, QuicLogInfo
0x140041696  call    McTemplateU0s_EtwWriteTransfer
0x14004169b  lea     r8, [rsp+168h+var_138]
0x1400416a0  mov     rdx, rdi
0x1400416a3  mov     ecx, ebp
0x1400416a5  call    QuicSettingsVersionSettingsToInternal
0x1400416aa  test    eax, eax
0x1400416ac  js      loc_1400417B3
0x1400416b2  mov     r8b, 1
0x1400416b5  lea     rcx, [rsi+60h]
0x1400416b9  mov     dl, r8b
0x1400416bc  lea     r9, [rsp+168h+var_138]
0x1400416c1  call    QuicSettingApply
0x1400416c6  test    al, al
0x1400416c8  jnz     short loc_1400416CF
0x1400416ca  mov     ebx, 0C000000Dh
0x1400416cf  lea     rcx, [rsp+168h+var_138]
0x1400416d4  call    QuicSettingsCleanup
0x1400416d9  mov     eax, ebx
0x1400416db  jmp     loc_1400417B3
0x1400416e0  test    rdi, rdi
0x1400416e3  jz      loc_1400417AE
0x1400416e9  cmp     ebp, 51h ; 'Q'
0x1400416ec  jb      loc_1400417AE
0x1400416f2  mov     rcx, [rsi+30h]; phCredential
0x1400416f6  test    rcx, rcx
0x1400416f9  jnz     short loc_140041705
0x1400416fb  mov     eax, 0C0000184h
0x140041700  jmp     loc_1400417B3
0x140041705  mov     rax, 948B0FCD6E9E0653h
0x14004170f  mov     r8, rbp
0x140041712  mul     rbp
0x140041715  sub     r8, rdx
0x140041718  shr     r8, 1
0x14004171b  add     r8, rdx
0x14004171e  mov     rdx, rdi
0x140041721  shr     r8, 6
0x140041725  call    CxPlatTlsSecConfigSetTicketKeys
0x14004172a  jmp     loc_1400417B3
0x14004172f  test    rdi, rdi
0x140041732  jz      short loc_1400417AE
0x140041734  test    cs:byte_14005C48E, 40h
0x14004173b  jz      short loc_14004177A
0x14004173d  lea     r9, aCnfgPSettingNe; "[cnfg][%p] Setting new settings"
0x140041744  mov     [rsp+168h+var_148], rsi
0x140041749  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14004174d  lea     rcx, [rsp+168h+DstBuf]; DstBuf
0x140041755  mov     edx, 80h; SizeInBytes
0x14004175a  call    cs:__imp__snprintf_s
0x140041761  nop     dword ptr [rax+rax+00h]
0x140041766  lea     r8, [rsp+168h+DstBuf]
0x14004176e  lea     rdx, QuicLogInfo
0x140041775  call    McTemplateU0s_EtwWriteTransfer
0x14004177a  lea     r8, [rsp+168h+var_138]
0x14004177f  mov     rdx, rdi
0x140041782  mov     ecx, ebp
0x140041784  call    QuicSettingsSettingsToInternal
0x140041789  test    eax, eax
0x14004178b  js      short loc_1400417B3
0x14004178d  mov     r8b, 1
0x140041790  lea     rcx, [rsi+60h]
0x140041794  mov     dl, r8b
0x140041797  lea     r9, [rsp+168h+var_138]
0x14004179c  call    QuicSettingApply
0x1400417a1  neg     al
0x1400417a3  sbb     eax, eax
0x1400417a5  not     eax
0x1400417a7  and     eax, 0C000000Dh
0x1400417ac  jmp     short loc_1400417B3
0x1400417ae  mov     eax, 0C000000Dh
0x1400417b3  mov     rcx, [rsp+168h+var_28]
0x1400417bb  xor     rcx, rsp; StackCookie
0x1400417be  call    __security_check_cookie
0x1400417c3  mov     rbx, [rsp+168h+arg_8]
0x1400417cb  add     rsp, 150h
0x1400417d2  pop     rdi
0x1400417d3  pop     rsi
0x1400417d4  pop     rbp
0x1400417d5  retn
```
