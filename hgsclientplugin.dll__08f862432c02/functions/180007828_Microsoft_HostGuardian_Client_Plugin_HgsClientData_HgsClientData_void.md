# Microsoft::HostGuardian::Client::Plugin::HgsClientData::~HgsClientData(void)

- ea: `0x180007828`
- end: `0x180007859`
- name: `??1HgsClientData@Plugin@Client@HostGuardian@Microsoft@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(char **this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aec1`
- `0x18000af2f`

## callees

- `0x180006260`
- `0x1800062ec`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::HgsClientData::~HgsClientData(char **this)
{
  std::vector<std::wstring>::~vector<std::wstring>((__int64)(this + 11));
  std::vector<std::wstring>::~vector<std::wstring>((__int64)(this + 8));
  std::wstring::~wstring(this + 4);
  std::wstring::~wstring(this);
}

```

## disassembly

```asm
0x180007828  push    rbx
0x18000782a  sub     rsp, 20h
0x18000782e  mov     rbx, rcx
0x180007831  add     rcx, 58h ; 'X'
0x180007835  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18000783a  lea     rcx, [rbx+40h]
0x18000783e  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180007843  lea     rcx, [rbx+20h]
0x180007847  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000784c  mov     rcx, rbx
0x18000784f  add     rsp, 20h
0x180007853  pop     rbx
0x180007854  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
